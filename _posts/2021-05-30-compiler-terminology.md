---
published: false
title: Compiler and optimization terminology
tags: java performance
---
## Compiler / Optimisation Terminology

| Term        | Description           | 
| ------------- |:-------------:| 
| Lowering      | Rewriting complex constructs in terms of simpler ones | 
| Idiom      | A set of constructs that means something different when together      | 
| Inline | Replace a function call site with the body of the called function      | 
| Constant Folding | Process of recognizing and evluating (constant) expressions at compile time | 
| Constant Propogation | Proess of substituting the values of known constants in expressions at compile time |
| Hoisting | Move Loop-invatiant expressions out of the loops |
| Forward Store | Move stores to global variables out of the loops to reduce memory bandwidth requirements |
| Escape Analysis | Analyze the scope of an object - "new" objects when talking about on-stack allocation, but also a prerequisite for optimizations around concurrency/locking |




Sources

- [Bartosz Adamczewski @badamxzewski01](https://twitter.com/badamczewski01/status/1398541427018194945)
- [DZone Grzegorz Mirek](https://dzone.com/articles/escape-analysis)