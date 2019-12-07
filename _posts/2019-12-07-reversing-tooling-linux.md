---
published: true
tags: reversing linux
---
## Tools and tips for reversing/low-level inspection

# Tooling

The obvious: hexdump, strings

| Command | Description                                                                       |
|:--------|:----------------------------------------------------------------------------------|
| xxd     | better hexdump, also convert to/from binary<->hexdump                             |
| od      | dump files as (e.g) words, ints, octal, big/little endian etc                     |
| read    | take single line stdin/FD and assign delimited fields to supplied named variables |


### Various  examples

`read v1 v2 < <(od -tuS -An -N4 filename)` reads od's output into shell variables v1 and v2

# Visualisation

Simple graphics formats with [basic headers/formats](https://en.wikipedia.org/wiki/Netpbm_format#File_format_description) you can generate from the shell
- .PGM Portable Greymap 
- .PBM Portable Bitmap 
- .PPM Portable Pixmap
