---
layout: post
title: "JDK notable changes"
date: 2019-11-22
---

## [JDK 14](https://openjdk.java.net/projects/jdk/14/)

| Notable | Feature                                           |                      Description                       | Link                                         |
|:-------:|:--------------------------------------------------|:------------------------------------------------------:|:---------------------------------------------|
|    ✅    | Deprecating `parallel scavenge` & `serial old` gc |                                                        | [JEP 366](https://openjdk.java.net/jeps/366) |
|    ✅    | `switch` expresions (standard)                    |                                                        | [JEP 361](https://openjdk.java.net/jeps/361) |
|         | Records                                           |                                                        | [JEP 359](https://openjdk.java.net/jeps/359) |
|         | Packaging tool                                                                                            || [JEP 343](https://openjdk.java.net/jeps/343) |
|         | `instanceof` pattern matching                                                                             || [JEP 305](https://openjdk.java.net/jeps/305) |
|         | text blocks                                       |                   Multi-line strings                   | [JEP 368](https://openjdk.java.net/jeps/368) |
|    ✅    | ? Remove CMS GC                                   | This is big, which GC to use for "zero GC" programming | [JEP 363](https://openjdk.java.net/jeps/363) |
|         | ? NUMA aware G1                                   |                                                        | [JEP 345](https://openjdk.java.net/jeps/345) |
|         | ? Non-Volatile Mapped Byte Buffers                |                                                        | [JEP 352](https://openjdk.java.net/jeps/352) |
|         | ? Helpful NPEs                                    | Tells you which part of a compound statement was null  | [JEP 358](https://openjdk.java.net/jeps/358) |

## [JDK 13](https://openjdk.java.net/projects/jdk/13/)

| Notable | Feature                       |                    Description                    | Link                                         |
|:-------:|:------------------------------|:-------------------------------------------------:|:---------------------------------------------|
|    ✅    | `switch` expresions (preview) |                                                   | [JEP 354](https://openjdk.java.net/jeps/354) |
|         | AppCDS (class sharing)        |           Class Data Sharing extension            | [JEP 350](https://openjdk.java.net/jeps/350) |
|         | text blocks (preview)         |                Multi-line strings                 | [JEP 368](https://openjdk.java.net/jeps/368) |
|         | ZGC releases unused storage   |                                                   | [JEP 351](https://openjdk.java.net/jeps/351) |
|    ✅    | Renewed socket API            | prep work for fibers, but easier to work with too | [JEP 353](https://openjdk.java.net/jeps/353) |


## [JDK 12](https://openjdk.java.net/projects/jdk/12/)

| Notable | Feature                           |                    Description                    | Link                                         |
|:-------:|:----------------------------------|:-------------------------------------------------:|:---------------------------------------------|
|    ✅    | Shenandoah GC (v1.0 experimental) | Now deprecated, v2.0 does not use Brooks pointers | [JEP 189](https://openjdk.java.net/jeps/189) |
|         | JMH benchmarkes for JDK features                                                     || [JEP 230](https://openjdk.java.net/jeps/230) |

## [JDK 11](https://openjdk.java.net/projects/jdk/11/)

| Notable | Feature                                 | Description | Link                                         |
|:-------:|:----------------------------------------|:-----------:|:---------------------------------------------|
|    ✅    | Epsilon GC                              |             | [JEP 318](https://openjdk.java.net/jeps/318) |
|    ✅    | HTTP Client                             |             | [JEP 321](https://openjdk.java.net/jeps/321) |
|    ✅    | Local-Variable Syntax for Lambda Params |    `var`    | [JEP 323](https://openjdk.java.net/jeps/323) |
|    ✅    | Low-Overhead Heap Profiling             |  Via JVMTI  | [JEP 331](https://openjdk.java.net/jeps/331) |
