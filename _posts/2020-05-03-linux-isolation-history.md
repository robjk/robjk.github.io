---
published: true
title: History of Linux Task Isolation
tags: linux performance
---
## A history of linux isolation mechanisms

[Matt Fleming](https://twitter.com/fleming_matt "twitter")

[pdf](/assets/The History of Linux Task Isolation.pdf)


- 2002: sched_setaffinity() / sched_getaffinity() (v2.5.8)
- 2004: isolcpus (v2.6.9)
- 2013: nohz_full, reduce timer ticks (v3.10)
- 2018: nohz_full, disable time ticks for isolated, single-task, cores (v4.17)
- 2020: prctl()

****nohz_full (2018)**** ticks can still be enabled by:
- Perf events
- Timers
- Scheduler (providing fairness, e.g. SCHED_RR and SCHED_OTHER)
- RCU
- Unstable clocks

Frederic Weisbecker
[youtube talk](https://www.youtube.com/watch?v=CJLA558npCU "Kernel Recipes 2015 - CPU isolation: state of the art")
[youtube talk](https://www.youtube.com/watch?v=ai-Avto0c0Q "Kernel Recipes 2018 - State of CPU Isolation")
