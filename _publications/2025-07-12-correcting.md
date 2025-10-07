---
title: "Correcting the LogQ Correction: Revisiting Sampled Softmax for Large-Scale Retrieval"
collection: publications
category: conferences # conferences, manuscripts
permalink: /publication/2025-07-12-correcting
excerpt: 'We revisited the derivation of the LogQ correction and identified an inconsistency related to the treatment of the positive sample in the denominator. By explicitly accounting for the positive sample during Monte Carlo sampling, we derived a new formulation that introduces an intuitive reweighting coefficient. Interestingly, the modified loss function achieves superior performance on both open datasets and large-scale proprietary benchmarks.'
date: 2025-07-12
venue: 'Proceedings of the 19th ACM Conference on Recommender Systems (RecSys’25)'
paperurl: 'https://arxiv.org/abs/2507.09331'
# citation: 'Your Name, You. (2024). &quot;Paper Title Number 3.&quot; <i>GitHub Journal of Bugs</i>. 1(3).'
---

Two-tower neural networks are a popular architecture for the retrieval stage in recommender systems. These models are typically trained with a softmax loss over the item catalog. However, in web-scale settings, the item catalog is often prohibitively large, making full softmax infeasible. A common solution is sampled softmax, which approximates the full softmax using a small number of sampled negatives.
One practical and widely adopted approach is to use in-batch negatives, where negatives are drawn from items in the current mini-batch. However, this introduces a bias: items that appear more frequently in the batch (i.e., popular items) are penalized more heavily.
To mitigate this issue, a popular industry technique known as logQ correction adjusts the logits during training by subtracting the log-probability of an item appearing in the batch. This correction is derived by analyzing the bias in the gradient and applying importance sampling, effectively twice, using the in-batch distribution as a proposal distribution. While this approach improves model quality, it does not fully eliminate the bias.
In this work, we revisit the derivation of logQ correction and show that it overlooks a subtle but important detail: the positive item in the denominator is not Monte Carlo-sampled - it is always present with probability 1. We propose a refined correction formula that accounts for this. Notably, our loss introduces an interpretable sample weight that reflects the model's uncertainty - the probability of misclassification under the current parameters. We evaluate our method on both public and proprietary datasets, demonstrating consistent improvements over the standard logQ correction.

Links
======
[[📄 arXiv](https://arxiv.org/abs/2507.09331) &nbsp;|&nbsp; [💻 GitHub](https://github.com/NonameUntitled/logq) &nbsp;|&nbsp; [📄 dl.acm.org](https://dl.acm.org/doi/10.1145/3705328.3748033)]