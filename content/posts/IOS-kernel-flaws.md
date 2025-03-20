---
title: "IOS kernel flaws"
date: 2025-01-12
categories: 
  - "security"
---

Back in 2012, Mark and I detailed a number of iOS kernel mitigations that were introduced in iOS 6 to prevent an attacker from leveraging well-known exploitation techniques such as the zone free list pointer overwrite. Most of these mitigations rely on entropy (of varying degree) provided by the kernel, and are therefore supported by a separate random number generator known as the **early\_random()** PRNG. As this generator is fundamental to the robustness of these mitigations, and has received additional improvements in iOS 7, it is unarguably a very interesting target that deserves further study.  


The initial version of the early random PRNG, found in iOS 6, leveraged a fairly simple generator that derived values directly from the CPU tick count and a seed (provided by iBoot). Although the generator was able to create somewhat unpredictable values, it had a serious defect in that the outputs were well-correlated, especially in the case of successively generated values. Additionally, the seed was only combined with the higher 32 bits of the output, hence the lower bits (typically the only part used on 32-bit iOS devices) were unaffected by the seed value. Thus, in an attempt to improve the early random PRNG in iOS 7, Apple decided to leverage an entirely new generator. Specifically, iOS 7 uses a linear congruential generator, a PRNG well-known both for its strengths and (notable) weaknesses.


An LCG's quality is essentially determined by its choice of parameters. Although the early random PRNG is clearly inspired by glibc **random\_r()**and ANSI C **rand()**, it is alarmingly weak in practice. Notably,**early\_random()** in iOS 7 can only produce 2^19 unique outputs, with a maximum period of 2^17 (length of sequence of unique outputs, before it starts over). This is well below the size of the possible output space (64-bits), and may allow an attacker to predict values with very little effort. In particular, we found that an unprivileged attacker, even when confined by the most restrictive sandbox, can recover arbitrary outputs from the generator and consequently bypass all the exploit mitigations that rely on the early random PRNG. These findings have been detailed in the following slides and white paper, and includes suggestions on how to improve **early\_random()** in future iOS versions.  
  

iPhone5S:~ mobile$ uname -a  
Darwin iPhone5S 14.0.0 Darwin Kernel Version 14.0.0: Fri Sep 27 23:08:32 PDT 2013; root:xnu-2423.3.12~1/RELEASE\_ARM64\_S5L8960X iPhone6,2 arm64 N53AP Darwin

iPhone5S:~ mobile$ ./prng -n 12 -v

\[+\] Attempting to recover permutation value

\[+\] Created pipe descriptor: 0x3

\[+\] Pipe inode: abd3422bc9e617e1

\[+\] Brute-forcing discarded bits

\[+\] Found match. Computing remaining states.

\[+\] PRNG output: abd342ab3da7acc1

\[+\] Backtracking to seed

\[+\] Dumping PRNG outputs

\------------------------------------------------------------------

 ## | Raw Output       | Value          | Type

\------------------------------------------------------------------

  0 |            32c98 |            32c98 | Initial seed (19 bits)

  1 |  f9e9a1a49ea4f48 |  f9e9a1a49ea0048 | Stack check guard

  2 | dee5a48c513eded6 |  535218c513eded7 | Zone poisoned cookie

  3 | 1b25a4953a4999bb |               10 | Zone factor

  4 | 9bdc5bb7688ddd79 | 3f0011b7688ddd78 | Zone nopoison cookie

  5 | 308c2370f7885f8e |              18e | Kernel map offset

  6 | 20b36d423abcad7c | 20b36d423abcad7c | Yarrow seed

  7 | abd342ab3da7acc1 | abd342ab3da7acc1 | VM permutation value

  8 | 896ac52d43cb1adf | 896ac52d43cb1adf | Buf permutation value

  9 | 68faae4648a60d54 | 68faae4648a60d54 | 

 10 | 7201cf787fba71a2 | 7201cf787fba71a2 | 

 11 | c4019241d4858d47 | c4019241d4858d47 |  
\------------------------------------------------------------------

