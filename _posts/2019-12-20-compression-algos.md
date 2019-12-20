---
published: true
tags: algorithms compression
---
## Compression algorithms

| Name/Link | Comment |
|-----------|---------|
| [LZ4 (java)](https://github.com/lz4/lz4-java) - [LZ4 (mainline)](https://lz4.github.io/lz4/) | LZ4 is lossless compression algorithm, providing compression speed > 500 MB/s per core (>0.15 Bytes/cycle). It features an extremely fast decoder, with speed in multiple GB/s per core (~1 Byte/cycle).  Java impl = minimal memory footprint |
| [Snappy](https://github.com/google/snappy) - [Java (JNI)](https://github.com/xerial/snappy-java) | Google's fast compressor, 250 MB/sec compression - trades off speed for compression size |
| [XZ](https://tukaani.org/xz/java.html) | High compression rate, slow, take care with memory footprint when decoding (dictionary array allocation) |
