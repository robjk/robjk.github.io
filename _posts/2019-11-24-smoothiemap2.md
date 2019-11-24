---
published: false
tags: algorithms java
---
## SmoothieMap2

> In this tradeoff space, SmoothieMap fares extremely well on the memory footprint: it‘s probably the leanest among all production hash table implementations ever written

> SmoothieMap doesn’t have rehashing in the first place: it grows smoothly as the entries are inserted. SmoothieMap also doesn’t have a load factor and performs equally well regardless of whether the expected population of the hash table is specified at the creation time or not

> The absence of rehash and the related latency spike was the main original goal of SmoothieMap which makes it useful in real-time applications

> On the other hand, SmoothieMap has relatively high non-memory related CPU cost of key search and insertion operations. It may be about 50% slower than java.util.HashMap.


[https://medium.com/@leventov/smoothiemap-2-the-lowest-memory-hash-table-ever-6bebd06780a3](https://medium.com/@leventov/smoothiemap-2-the-lowest-memory-hash-table-ever-6bebd06780a3)
