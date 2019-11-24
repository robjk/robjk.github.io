---
published: true
tags: algorithms
title: Concurrent 2-Trie
---
## Concurrent 2-Trie

> The concurrent 2-trie is a dictionary-like data structure that is designed and optimized specifically to be used for translation tables in file buffer pools. When the concurrent 2-trie replaced the lock-striped hop-scotch hash tables in the Neo4j file buffer pool, file buffer accesses became 30% faster.

> The concurrent 2-trie optimizes for the domain of file buffer translation tables by making the following observations: First, the file page identifiers form a sequence, starting from zero until the last page in the file. Second, files can only grow by being extended at the end. Third, most database deployments are able to fit the majority of their data in memory, and often the data set fits entirely in memory. This means the translation tables are usually densely packed.

[https://medium.com/@chrisvest/the-concurrent-2-trie-67deb2b57ba1](https://medium.com/@chrisvest/the-concurrent-2-trie-67deb2b57ba1)  
