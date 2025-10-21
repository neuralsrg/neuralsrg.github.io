---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* **MSc in Applied Mathematics and Computer Science**, Moscow State University, 2024 -- present
* **BSc in Applied Mathematics and Computer Science**, Moscow State University, 2020 -- 2024
  * Diploma with Honours
  * Thesis topics: Application of discrete mathematics and combinatorics in machine learning

Work experience
======
* **Middle Deep Learning Engineer**, RecSys R&D at Yandex, 2025 -- present
  * Research topics:
    * Generative Models
    * Scaling Laws
    * Quality-complexity tradeoffs for real-time recommendation models

* **Junior Deep Learning Engineer**, RecSys R&D at Yandex, 2024 -- 2025
  * Research topics:
    * Generative Models
    * Scaling Laws

* **Research Intern**, RecSys R&D at Yandex, 2024
  * Research topics: Graph Neural Network applications in web-scale recommender systems

* **Research Assistant**, Moscow State University, 2021 -- 2024
  * Research topics: Cognitive dynamics analysis and internal speech recognition

Research interests
======
* Information retrieval
* Recommender systems
* Debiasing in recommendations
* Conversational and explainable recommender systems
* Generative models and scaling laws
* Fairness and inclusion in recommendations
* General underlying mathematics of deep learning (e.g., Bayesian methods)

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Conferences & Academic Programs
======
* **RecSys'25**, Prague, Czech Republic. Sep 2025
  * [Blending Sequential Embeddings, Graphs, and Engineered Features: 4th Place Solution in RecSys Challenge 2025](https://neuralsrg.github.io/publication/2025-08-09-challenge)
  * [Correcting the LogQ Correction: Revisiting Sampled Softmax for Large-Scale Retrieval](https://neuralsrg.github.io/publication/2025-07-12-correcting)
* **ACM Europe School on Recommender Systems**, Vienna, Austria. Sep 2025
* **UMAP'25**, New York, USA. Jun 2025
  * PC member of Industry & Start-up Track

Competitions
======
* RecSys Challenge 2025 - 4th place
  * Paper: [Blending Sequential Embeddings, Graphs, and Engineered Features: 4th Place Solution in RecSys Challenge 2025](https://neuralsrg.github.io/publication/2025-08-09-challenge)
  * Talk: [4th Place Solution in RecSys Challenge 2025](https://neuralsrg.github.io/talks/2025-09-22-challenge)

Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>

Scholarships
======
* Individual Moscow Government Scholarship for Academic Achievements, 2020 -- 2021
* Increased state academic scholarship for outstanding academic achievements, 2022

<!-- Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul> -->
  
Other skills
======
* _Programming languages_: Python, C/C++, Assembly, basic knowledge of CUDA
* _Orchestrators_: Nirvana - at Yandex, I had experience training models on hundreds of GPUs
