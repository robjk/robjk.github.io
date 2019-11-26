---
published: false
tags: performance cpu
title: Implications of AVX vector instruction usage
---
## Implications of using AVX vector instructions

Twitter thread discussing Intel CPUs stepping down the clock to run vector ops, and the 2ms post completion hysterisis at the end

[https://twitter.com/11rcombs/status/1089322582816555009](https://twitter.com/11rcombs/status/1089322582816555009)

> okay very tangential but fun fact: when Intel CPUs are executing many 256-bit or 512-bit vector instructions, they downclock themselves by 10 to 40% to offset the increased current draw from powering up the upper lanes of the vector units

> so engineers writing tight assembly code have to be careful to only use those wider instructions when
(a) they know the gain will be larger than the clock loss
(b) the code will run for long enough to be worth the 2ms that the processor stays downclocked after you're finished

September 2018
[Lemire's take on usage](https://lemire.me/blog/2018/09/07/avx-512-when-and-how-to-use-these-new-instructions/)

3rd May 2018 take
[https://gist.github.com/rygorous/32bc3ea8301dba09358fd2c64e02d774](https://gist.github.com/rygorous/32bc3ea8301dba09358fd2c64e02d774)