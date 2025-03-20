---
title: "<div>Forking the RANDAO: Manipulating Ethereum's Distributed Randomness Beacon</div>"
date: 2025-01-10
categories: 
  - "cryptography"
  - "security"
tags: 
  - "cryptography"
  - "security"
---

ePrint Report: **Forking the RANDAO: Manipulating Ethereum's Distributed Randomness Beacon**  
_Ábel Nagy, János Tapolcai, István András Seres, Bence Ladóczki_

Proof-of-stake consensus protocols often rely on distributed randomness beacons (DRBs) to generate randomness for leader selection. This work analyses the manipulability of Ethereum's DRB implementation, RANDAO, in its current consensus mechanism. Even with its efficiency, RANDAO remains vulnerable to manipulation through the deliberate omission of blocks from the canonical chain. Previous research has shown that economically rational players can withhold blocks --~known as a block withholding attack or selfish mixing~-- when the manipulated RANDAO outcome yields greater financial rewards.  
  
We introduce and evaluate a new manipulation strategy, the RANDAO forking attack. Unlike block withholding, whereby validators opt to hide a block, this strategy relies on selectively forking out an honest proposer's block to maximize transaction fee revenues and block rewards. In this paper, we draw attention to the fact that the forking attack is significantly more harmful than selfish mixing for two reasons. Firstly, it exacerbates the unfairness among validators. More importantly, it significantly undermines the reliability of the blockchain for the average user by frequently causing already published blocks to be forked out. By doing so, the attacker can fork the chain without losing slots, and we demonstrate that these are later fully compensated for. Our empirical measurements, investigating such manipulations on Ethereum mainnet, revealed no statistically significant traces of these attacks to date.

Go to Source
