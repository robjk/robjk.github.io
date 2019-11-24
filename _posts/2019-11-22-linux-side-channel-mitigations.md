---
published: true
tags: linux performance
title: Linux boot - disable side-channel mitigations and restore speed
---
## Linux boot: disable side-channel mitigations and restore speed
[https://make-linux-fast-again.com](https://make-linux-fast-again.com)

As of today

> noibrs noibpb nopti nospectre_v2 nospectre_v1 l1tf=off nospec_store_bypass_disable no_stf_barrier mds=off tsx=on tsx_async_abort=off mitigations=off`

[Linux Reviews article on the topic](https://linuxreviews.org/HOWTO_make_Linux_run_blazing_fast_(again)_on_Intel_CPUs)

[Brendan Gregg's summary of the problem](http://www.brendangregg.com/blog/2018-02-09/kpti-kaiser-meltdown-performance.html)

> In this post I'll look at the Linux kernel page table isolation (KPTI) patches that workaround Meltdown: what overheads to expect, and ways to tune them. Much of my testing was on Linux 4.14.11 and 4.14.12 a month ago, before we deployed in production  

> Note that there are potentially four layers of overhead for Meltdown/Spectre, this is just one. They are:
- Guest kernel KPTI patches (this post)
- Intel microcode updates
- Cloud provider hypervisor changes (for cloud guests)
- Retpoline compiler changes
