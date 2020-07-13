---
published: true
tags: performance java linux
title: Java & Linux clocks - State of the world
---
## Java & Linux clocks - State of the world

Pulling together state of the world with respect to time sources in Linux and Java

**WIP, requires summarisation**

- [Measuring time, from Java to kernel and back (Jaromir Hamala ~dec 2019)](https://www.javaadvent.com/2019/12/measuring-time-from-java-to-kernel-and-back.html)
    ### available clock sources
    cat /sys/devices/system/clocksource/clocksource0/available_clocksource
    ### specify clock source
    echo tsc > /sys/devices/system/clocksource/clocksource0/current_clocksource


- [StackOverflow: Current time in microseconds](https://stackoverflow.com/a/35213339)
As of JDK 9 nanoseconds are available in Instant
bug ref: ([JDK-8068730 Increase the precision...](https://bugs.openjdk.java.net/browse/JDK-8068730)
Further updates occurred after this, JDK 15 interesting (see below)

- [Bill Torpey's blog: "Measuring Latency in Linux" (~2014)](http://btorpey.github.io/blog/2014/02/18/clock-sources-in-linux/)

Note this comment:
> For inter-machine timings, you’re pretty much stuck with the CLOCK_REALTIME clock source (the source for gettimeofday), since you presumably need a clock that is synchronized across the two (or more) machines you are testing. In this case, the accuracy of your timing measurements will obviously depend on how well the clock synchronization works, and in all but the best cases you’ll be lucky to get accuracy better than some small number of microseconds.

You could argue ptp would keep your measurements close but given alternative options (i.e. corvile) should you really be attempting to measure nanoseconds between machines via their internal clocks...

- [Java Bug Database: JDK-8242504 : Enhance the system clock to nanosecond precision (Fixed JDK 15)](https://bugs.java.com/bugdatabase/view_bug.do?bug_id=8242504)
- [Java Bug Database: JDK-8185891 : System.currentTimeMillis() is slow on Linux, especially with the HPET time source (~2015 originally, David Holmes ftw)](https://bugs.openjdk.java.net/browse/JDK-8185891?focusedCommentId=14107380&page=com.atlassian.jira.plugin.system.issuetabpanels%3Acomment-tabpanel#comment-14107380)

- [Java Bug Database: issues labelled 'time'](https://bugs.openjdk.java.net/issues/?jql=labels+%3D+time)
