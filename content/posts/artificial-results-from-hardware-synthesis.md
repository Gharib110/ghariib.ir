---
title: "Artificial Results From Hardware Synthesis"
date: 2025-01-22
categories: 
  - "cryptography"
  - "security"
tags: 
  - "cryptography"
  - "security"
---

ePrint Report: **Artificial Results From Hardware Synthesis**  
_Ahmed Alharbi, Charles Bouillaguet_

In this paper, we revisit venerable lower-bounds on the $AT$ or $AT^2$ performance metric of hardware circuits. A series of works started in the late 1970's has established that if a hardware circuit of area $A$ computes a function $f : {0, 1}^n rightarrow {0, 1}^m$ in $T$ clock cycles, then $AT^2$ is asymptotically larger than (a form of) the communication complexity of $f$. These lower-bounds ignore the active component of the circuit such as the logic gates and only take into account the area of the wiring.  
  
However, it seems that it is common practice to report the performance characteristics of hardware designs after synthesis, namely after having \`\`compiled'' the design into the topological description of a hardware circuit made of standard cells. The area of the cells can be be determined with certainty, whereas the area occupied by the wires cannot. This may leads to optimistic performance figures, that may even violate the old lower-bounds. In this paper, we take the case of the Möbius transform as a case study, following the work of Banik and Regazzoni in TCHES, 2024(2) who presented hardware designs that implement it. We first determine the communication complexity of the Möbius transform. Then, following the old methodology, we derive lower-bounds on the area (in $mu m^2$) of any circuit that implement the operation using several open Process Design Kits for ASIC production. For large enough instances, the wires provably occupy more area than the logic gates themselves. This invalidate previous theoretical claims about the performance of circuits implementing the Möbius transform.  
  
Fundamentally, the root cause of the contradiction between \`\`VLSI-era'' lower-bounds and current performance claims is that the lower-bounds apply to a geometric description of the circuit where the length of wiring is known, while it is common to report performance results on the basis of hardware synthesis alone, where a topological description of the circuit has been obtained but the actual length of wires is unknown.

Go to Source
