---
title: "poqeth: Efficient, post-quantum signature verification on Ethereum"
date: 2025-01-22
categories: 
  - "cryptography"
  - "security"
tags: 
  - "cryptography"
  - "security"
---

ePrint Report: **poqeth: Efficient, post-quantum signature verification on Ethereum**  
_Ruslan Kysil, István András Seres, Péter Kutas, Nándor Kelecsényi_

This work explores the application and efficient deployment of (standardized) post-quantum (PQ) digital signature algorithms in the blockchain environment. Specifically, we implement and evaluate four PQ signatures in the Ethereum Virtual Machine: W-OTS$^{+}$, XMSS, SPHINCS+, and MAYO. We focus on optimizing the gas costs of the verification algorithms as that is the signature schemes' only algorithm executed on-chain, thus incurring financial costs (transaction fees) for the users. Hence, the verification algorithm is the signature schemes' main bottleneck for decentralized applications.  
  
We examine two methods to verify post-quantum digital signatures on-chain. Our practical performance evaluation shows that full on-chain verification is often prohibitively costly. Naysayer proofs (FC'24) allow a novel optimistic verification mode. We observe that the Naysayer verification mode is generally the cheapest, at the cost of additional trust assumptions. We release our implementation called poqeth as an open-source library.

Go to Source
