---
title: "ProbeShooter: A New Practical Approach for Probe Aiming"
date: 2025-01-08
categories: 
  - "cryptography"
  - "security"
tags: 
  - "cryptography"
  - "security"
---

ePrint Report: **ProbeShooter: A New Practical Approach for Probe Aiming**  
_Daehyeon Bae, Sujin Park, Minsig Choi, Young-Giu Jung, Changmin Jeong, Heeseok Kim, Seokhie Hong_

Electromagnetic side-channel analysis is a powerful method for monitoring processor activity and compromising cryptographic systems in air-gapped environments. As analytical methodologies and target devices evolve, the importance of leakage localization and probe aiming becomes increasingly apparent for capturing only the desired signals with a high signal-to-noise ratio. Despite its importance, there remains substantial reliance on unreliable heuristic approaches and inefficient exhaustive searches. Furthermore, related studies often fall short in terms of feasibility, practicality, and performance, and are limited to controlled DUTs and low-end MCUs.  
  
To address the limitations and inefficiencies of the previous approaches, we propose a novel methodology―${rm P{tiny ROBE}S{tiny HOOTER}}$―for leakage localization and probe aiming. This approach leverages new insights into the spatial characteristics of amplitude modulation and intermodulation distortion in processors. As a result, ${rm P{tiny ROBE}S{tiny HOOTER}}$ provides substantial improvements in various aspects: $boldsymbol 1)$ it is applicable to not only simple MCUs but also complex SoCs, $boldsymbol 2)$ it effectively handles multi-core systems and dynamic frequency scaling, $boldsymbol 3)$ it is adoptable to uncontrollable DUTs, making it viable for constrained real-world attacks, and $boldsymbol 4)$ it performs significantly faster than previous methods. To demonstrate this, we experimentally evaluate ${rm P{tiny ROBE}S{tiny HOOTER}}$ on a high-end MCU (the NXP i.MX RT1061 featuring a single ARM Cortex-M7 core) and a complex SoC (the Broadcom BCM2711 equipped with the Raspberry Pi 4 Model B, featuring four ARM Cortex-A72 cores).

Go to Source
