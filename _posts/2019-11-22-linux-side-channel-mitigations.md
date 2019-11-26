---
published: true
tags: linux performance
title: Disable side-channel mitigations
---
## Linux boot: disable side-channel mitigations and restore speed
[https://make-linux-fast-again.com](https://make-linux-fast-again.com)

As of today

> noibrs noibpb nopti nospectre_v2 nospectre_v1 l1tf=off nospec_store_bypass_disable no_stf_barrier mds=off tsx=on tsx_async_abort=off mitigations=off`

[Linux Reviews article on the topic](https://linuxreviews.org/HOWTO_make_Linux_run_blazing_fast_(again)_on_Intel_CPUs)

---

[Brendan Gregg's summary of the problem with KPTI](http://www.brendangregg.com/blog/2018-02-09/kpti-kaiser-meltdown-performance.html)

> In this post I'll look at the **Linux kernel page table isolation (KPTI)** patches that workaround Meltdown: what overheads to expect, and ways to tune them. Much of my testing was on Linux 4.14.11 and 4.14.12 a month ago, before we deployed in production  

> Note that there are potentially four layers of overhead for Meltdown/Spectre, this is just one. They are:
- Guest kernel KPTI patches (this post)
- Intel microcode updates
- Cloud provider hypervisor changes (for cloud guests)
- Retpoline compiler changes

Excellent examples of investigating kernel performance: 
- Syscall rate (perf)
>If you don't know your syscall rate, you can measure it, eg, using perf:  
`sudo perf stat -e raw_syscalls:sys_enter -a -I 1000`  
This shows the system-wide syscall rate. Divide it by the CPU count (as reported by mpstat, etc) for the per-CPU rate. Then by 1000 for the graph above. Note that this perf stat command causes some overhead itself, which may be noticeable for high syscall rates (>100k/sec/CPU). You can switch to ftrace/mcount to measure it with lower overhead if that is desired. For example, using my perf-tools:  
`sudo ./perf-tools/bin/funccount -i 1 -d 10 '[sS]y[sS]_*'`      
- Context Switch & Page Fault Rate (/proc & sar)  
`sar -wB 1`  
- Working Set Size (hot data) using custom microbenchmark
> [https://github.com/brendangregg/pmc-cloud-tools](https://github.com/brendangregg/pmc-cloud-tools) (`tlbstat -C0 1`)  
- Cache Access Pattern (PMC)

Related reading and references:
- [PCID is now a critical performance/security feature on x86](http://archive.is/ma8Iw)
- [PMC Cloud Tools](https://github.com/brendangregg/pmc-cloud-tools)

> PCID is a hardware feature that has been available on Intel CPUs and that it attaches an address space tag to TLB entries and thus allows the hardware to skip TLB flushes when it context-switches. x86's PCID is far too short to uniquely identify a process, and it can't even really uniquely identify a running process because there are monster systems with over 4096 CPUs. To make matters worse, past attempts to use all 12 PCID bits have resulted in slowdowns instead of speedup  

>This release uses PCID differently. It uses a PCID to identify a recently-used mm on a per-cpu basis. An mm has no fixed PCID binding at all; instead, it is given a fresh PCID each time it's loaded except in cases where the kernel wants to preserve the TLB, in which case it reuses a recent value.