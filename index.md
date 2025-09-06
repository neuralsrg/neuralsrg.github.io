---
layout: default
title: Home
---

# About Me

As a Master of Science student, I’ve had the honor of working with leading AI practitioners at Yandex. Together, we build and improve recommender systems across various Yandex platforms — including Yandex Music, Yandex Market, and more. We’re always excited to share our experience with the wider community of recommender system developers.


# Papers

**Blending Sequential Embeddings, Graphs, and Engineered Features: 4th Place Solution in RecSys Challenge 2025** (2025)

<p class="paper-desc">
We are excited to share our work from the RecSys Challenge 2025! In our solution, we combined the Transformer, TwHIN graph neural network, DCN-v2, and hundreds of carefully engineered numeric features. We discuss feature engineering in detail in the Appendix, which one of our reviewers called a "goldmine of practical insights". We will be presenting our paper at RecSys 2025 in Prague.
</p>

[📄 arXiv](https://arxiv.org/abs/2508.06970) &nbsp;|&nbsp; [📄 dl.acm.org](https://dl.acm.org/doi/10.1145/3758126.3758131)

---

**Scaling Recommender Transformers to One Billion Parameters** (2025)

<p class="paper-desc">
We proposed a two-stage training approach for a ranking causal transformer. In the first stage, we pretrain the model on a fundamental next-token prediction task, which is essential for enabling scale-up of the encoder. In the second stage, we fine-tune the model on a pairwise ranking objective. We evaluate performance across four model sizes with exponentially increasing encoder capacity and demonstrate adherence to the scaling law.
</p>

[📄 arXiv](https://www.arxiv.org/abs/2507.15994)

---

**Correcting the LogQ Correction: Revisiting Sampled Softmax for Large-Scale Retrieval** (2025)

<p class="paper-desc">
We revisited the derivation of the LogQ correction and identified an inconsistency related to the treatment of the positive sample in the denominator. By explicitly accounting for the positive sample during Monte Carlo sampling, we derived a new formulation that introduces an intuitive reweighting coefficient. Interestingly, the modified loss function achieves superior performance on both open datasets and large-scale proprietary benchmarks.
</p>

[📄 arXiv](https://arxiv.org/abs/2507.09331) &nbsp;|&nbsp; [💻 GitHub](https://github.com/NonameUntitled/logq) &nbsp;|&nbsp; [📄 dl.acm.org](https://dl.acm.org/doi/10.1145/3705328.3748033)


# Conferences

- RecSys'25 Author of:
    - Short papers track *Correcting the LogQ Correction: Revisiting Sampled Softmax for Large-Scale Retrieval*
    - RecSys Challenge track *Blending Sequential Embeddings, Graphs, and Engineered Features: 4th Place Solution in RecSys Challenge 2025*
- UMAP'25 – Industry Track PC member

# Other events

- ACM Europe School on Recommender Systems, 2025
- RecSys Challenge 2025 - 4th place
