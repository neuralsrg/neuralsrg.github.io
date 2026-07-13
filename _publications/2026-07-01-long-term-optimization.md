---
title: "Long-Term Optimization for Large-Scale Generative Retrieval with Off-Policy REINFORCE"
collection: publications
category: conferences # conferences, manuscripts
permalink: /publication/2026-07-01-long-term-optimization
conference_label: KDD’26 Workshop
location: Jeju Island, Republic of Korea
conference_date_label: August 2026
conference_note: 5th Workshop on End-to-End Customer Journey Optimization
authors: 'Artem Matveev, <strong>Sergei Makeev</strong>, Aleksei Krasilnikov, Vladimir Baikalov, Sergei Liamaev, Kirill Khrylchenko'
excerpt: 'In this paper, we trained an RL agent using off-policy REINFORCE to maximize per-trajectory rewards. We also applied off-policy evaluation methods for RL, which is novel to recommendation systems. Our results demonstrate that session-wise optimization yields better off-policy evaluation metrics than maximizing immediate rewards, given the same amount of data, training time, and compute.'
news_excerpt: >-
  This paper was noted by Sumit Kumar on <a href="https://x.com/_reachsumit/status/2074365460016140529?s=46">x.com</a> and included in his <a href="https://recsys.substack.com/p/why-late-interaction-retrieval-is">Top Information Retrieval Papers of the Week</a> rating. After its release, it was promptly cited by some scientific websites (e.g., <a href="https://gist.science/paper/2607.02818">gist.science</a>, <a href="https://www.moltbook.com/post/665d8197-68b4-4f9b-8fcc-c204f3983751">moltbook.com</a>, <a href="https://chatpaper.com/paper/307865">chatpaper.com</a>).
date: 2026-07-01
venue: '5th Workshop on End-to-End Customer Journey Optimization at KDD’26'
---
Generative retrieval models are often trained to predict the next positive interaction of a user, consequently maximizing the immediate reward given to the recommender agent. This can be viewed as searching for a local optimum within the space of user interests. A more principled approach is to maximize the reward per trajectory (i.e., the user session), which can lead to a globally better solution than a greedy strategy. In this paper, we trained an RL agent using off-policy REINFORCE and evaluated it with off-policy evaluation methods, which is new to recommendation systems. Our results demonstrate that session-wise optimization yields better off-policy evaluation metrics than maximizing immediate rewards, given the same amount of data, training time, and compute.

Links
======
[[📄 arXiv](https://arxiv.org/abs/2607.02818)]