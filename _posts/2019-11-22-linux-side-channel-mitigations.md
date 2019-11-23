---
published: true
tags: linux performance
---
## Linux boot: disable side-channel mitigations and restore speed
[https://make-linux-fast-again.com](https://make-linux-fast-again.com)

As of today

`noibrs noibpb nopti nospectre_v2 nospectre_v1 l1tf=off nospec_store_bypass_disable no_stf_barrier mds=off tsx=on tsx_async_abort=off mitigations=off`

[Linux Reviews article on the topic](https://linuxreviews.org/HOWTO_make_Linux_run_blazing_fast_(again)_on_Intel_CPUs)
