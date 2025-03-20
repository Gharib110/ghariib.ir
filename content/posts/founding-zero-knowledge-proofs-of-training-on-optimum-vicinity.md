---
title: "Founding Zero-Knowledge Proofs of Training on Optimum Vicinity"
date: 2025-01-15
categories: 
  - "cryptography"
  - "security"
tags: 
  - "cryptography"
  - "security"
---

ePrint Report: **Founding Zero-Knowledge Proofs of Training on Optimum Vicinity**  
_Gefei Tan, Adrià Gascón, Sarah Meiklejohn, Mariana Raykova, Xiao Wang, Ning Luo_

Zero-knowledge proofs of training (zkPoT) allow a party to prove that a model is trained correctly on a committed dataset without revealing any additional information about the model or the dataset. Existing zkPoT protocols prove the entire training process in zero knowledge; i.e., they prove that the final model was obtained in an iterative fashion starting from the training data and a random seed (and potentially other parameters) and applying the correct algorithm at each iteration. This approach inherently requires the prover to perform work linear to the number of iterations.  
  
In this paper, we take a different approach to proving the correctness of model training. Our approach is motivated by efficiency but also more urgently by the observation that the prover's ability to pick the random seed used for training introduces the potential for it to bias the model. In other words, if the input to the training algorithm is biased, the resulting model will be biased even if the prover correctly ran the training algorithm. Rather than prove the correctness of the training process, we thus directly prove the correctness of the training model using a notion we call optimum vicinity, which bounds the distance between the trained model and the mathematically optimal model for models that can be viewed as the solution to a convex optimization problem. We show both theoretically and experimentally that this ensures the trained model behaves similarly to the optimal model, and show this is not true for existing approaches. We also demonstrate significant performance improvements as compared to the existing zkPoT paradigm: the statement proven in ZK in our protocol has a size independent of the number of training iterations, and our Boolean (respectively arithmetic) circuit size is up to $246times$ (respectively $5times$) smaller than that of a baseline zkPoT protocol that verifies the whole training process.

Go to Source
