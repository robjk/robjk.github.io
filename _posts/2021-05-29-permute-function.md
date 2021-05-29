---
published: true
title: Andrew Kensler’s permute function
tags: algorithms gfx
---
## Description of Andrew Kensler’s permute function

> You want to iterate over k items of an array of length n, in random order, where k ≤ n. Those k items cannot contain duplicates from the original array (they must each correspond to a unique index). Or, you want to get a random sample of kk items without replacement.

[Andrew Helmer's explanation](https://andrew-helmer.github.io/permute/)

[64 bit improvement](https://github.com/camel-cdr/cauldron/blob/main/tools/random/permute/README.md)

	uint32_t get_mask(uint32_t len) {
	  uint32_t mask = len-1;
	  mask |= mask >> 1;
	  mask |= mask >> 2;
	  mask |= mask >> 4;
	  mask |= mask >> 8;
	  mask |= mask >> 16;
	  return mask;
	}

	uint32_t hash(uint32_t idx, uint32_t mask, uint32_t seed) {
	  idx ^= seed; idx *= 0xe170893d;
	  idx ^= seed >> 16;
	  idx ^= (idx & mask) >> 4;
	  idx ^= seed >> 8; idx *= 0x0929eb3f;
	  idx ^= seed >> 23;
	  idx ^= (idx & mask) >> 1; idx *= 1 | seed >> 27;
	  idx *= 0x6935fa69;
	  idx ^= (idx & mask) >> 11; idx *= 0x74dcb303;
	  idx ^= (idx & mask) >> 2; idx *= 0x9e501cc3;
	  idx ^= (idx & mask) >> 2; idx *= 0xc860a3df;
	  idx &= mask;
	  idx ^= idx >> 5;
	  return idx;
	}

	uint32_t permute(uint32_t idx, uint32_t len, uint32_t seed) {
	  uint32_t mask = get_mask(len);
	  do {
	    idx = hash(idx, mask, seed);
	  } while (idx >= len);
      return (idx + seed) % len;
    }