---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

{% assign conference_papers = site.publications | where: "category", "conferences" | sort: "path" | reverse %}
{% assign professional_service = site.professional_service | sort: "path" | reverse %}
{% assign patents = site.patents | sort: "path" | reverse %}
{% assign competitions = site.competitions | sort: "path" | reverse %}
{% assign teaching_items = site.teaching | sort: "path" | reverse %}
{% assign grants = site.grants | sort: "path" | reverse %}

<style>
  .cv-entry-list {
    padding-left: 1.25rem;
  }

  .cv-entry-list > li {
    margin-bottom: 0.85rem;
  }

  .cv-entry-detail {
    margin: 0.15rem 0 0 1.25rem;
  }

  .cv-entry-detail p {
    margin: 0;
  }
</style>

<div class="cv-download-links">
  <a href="{{ base_path }}/cv/sergei_makeev_cv.pdf" class="btn btn--primary">Download CV as PDF</a>
</div>

Research Interests
======
Information retrieval, reinforcement learning, recommender systems, large language models, generative models and scaling laws, and the mathematical foundations of deep learning.

Education
======
* **MSc in Applied Mathematics and Computer Science**, Moscow State University, Faculty of Computational Mathematics and Cybernetics, 2024 -- 2026
  * Diploma with Honours
  * Thesis topic: Approximation of softmax activation function in recommendation problem
* **BSc in Applied Mathematics and Computer Science**, Moscow State University, Faculty of Computational Mathematics and Cybernetics, 2020 -- 2024
  * Diploma with Honours
  * Thesis topic: Application of discrete mathematics and combinatorics in machine learning

Work experience
======
* **Senior Researcher**, AI VK, 2026 -- present
  * Part of a research team led by [Prof. Dr. Alexander D’yakonov](https://www.kaggle.com/dyakonov), formerly world’s #1 rank on Kaggle. Research topics: generative retrieval and reinforcement learning in recommender systems.
    * Co-authored [Long-Term Optimization for Large-Scale Generative Retrieval with Off-Policy REINFORCE](https://neuralsrg.github.io/publication/2026-07-01-long-term-optimization), accepted to the 5th Workshop on End-to-End Customer Journey Optimization at KDD 2026.
* **Senior Deep Learning Engineer**, RecSys R&D at Yandex, 2024 -- 2026
  * Worked under the leadership of [Kirill Khrylchenko](https://www.linkedin.com/in/kirill-khrylchenko/). Research topics: generative models and scaling laws, and linear attention in real-time recommendation models.
    * Part of the team that developed [Argus](https://neuralsrg.github.io/publication/2026-07-05-argus). Argus increased TLT at Yandex Music by +2.26% and like likelihood by +6.37%. It was later adapted by our colleagues to nearly every recommendation-based Yandex product (e.g., e-commerce +1.7% GMV, food-tech services +2.1% GMV, and others).
    * Worked on quality-complexity trade-offs for recommendation models, co-authoring [Gated Bidirectional Linear Attention for Generative Retrieval](https://neuralsrg.github.io/publication/2026-06-08-gbla).
    * Worked on pretraining large-scale generative recommender models.

* **Research Intern**, RecSys R&D at Yandex, 2024
  * Research topic: applications of graph neural networks in web-scale recommender systems.

* **Research Assistant**, Moscow State University, 2021 -- 2024
  * Research topics: cognitive dynamics analysis and internal speech recognition under Russian Science Foundation grants [#20-18-00067](https://rscf.ru/project/LXjuaL8yl_MKyMwV-E0AYmYXKZ7dVATTIy5v_6WfDOq3PZJVv6H2gRUOxla_daUJ4bgTN-xp/) and [#20-18-00067-Π](https://rscf.ru/project/OwNy03bhBYAiNgcRD1Lq9DYlzpziFaDtdi0LjD-lDfhmGp1fntBfNIA3DdjvFBf32QgMbnrg/), under the supervision of [Dr. Alexander Vartanov](https://www.researchgate.net/profile/Vartanov-Alexander).

Publications
======

<ul class="cv-entry-list">
  {% for paper in conference_papers %}
    <li>
      {% if paper.conference_label %}<strong>{{ paper.conference_label }}</strong>{% endif %}{% if paper.location %}, {{ paper.location }}{% endif %}{% if paper.conference_date_label %}. {{ paper.conference_date_label }}{% endif %}
      <div class="cv-entry-detail">
        <div><a href="{{ base_path }}{{ paper.url }}">{{ paper.title }}</a>{% if paper.conference_note %}, <i>{{ paper.conference_note }}</i>{% endif %}</div>
        <div>{{ paper.authors }}</div>
      </div>
    </li>
  {% endfor %}
</ul>

Professional Service
======

<ul class="cv-entry-list">
  {% for service in professional_service %}
    <li>
      <strong>{{ service.title }}</strong>{% if service.location %}, {{ service.location }}{% endif %}{% if service.date_label %}. {{ service.date_label }}{% endif %}
      {% if service.description %}<div class="cv-entry-detail">{{ service.description }}</div>{% endif %}
    </li>
  {% endfor %}
</ul>

Patents
======

<ul class="cv-entry-list">
  {% for patent in patents %}
    <li>
      {% if patent.date_label %}{{ patent.date_label }}. {% endif %}{% if patent.link %}<a href="{{ patent.link }}">{{ patent.title }}</a>{% else %}{{ patent.title }}{% endif %}
      <div class="cv-entry-detail">{{ patent.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>
    </li>
  {% endfor %}
</ul>

Competitions
======

<ul class="cv-entry-list">
  {% for competition in competitions %}
    <li>
      {% if competition.date_label %}{{ competition.date_label }}. {% endif %}{% if competition.link %}<a href="{{ competition.link }}">{{ competition.title }}</a>{% else %}{{ competition.title }}{% endif %}
      <div class="cv-entry-detail">{{ competition.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>
    </li>
  {% endfor %}
</ul>

Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>

Teaching
======

<ul class="cv-entry-list">
  {% for item in teaching_items %}
    <li>
      <strong><a href="{{ base_path }}{{ item.url }}">{{ item.title }}</a></strong>{% if item.type %}, {{ item.type }}{% endif %}{% if item.venue %}, {{ item.venue }}{% endif %}{% if item.location %}, {{ item.location }}{% endif %}{% if item.date %}. {{ item.date | date: "%B %Y" }}{% endif %}
      <div class="cv-entry-detail">{{ item.content | markdownify }}</div>
    </li>
  {% endfor %}
</ul>

Research in News and Social Media
======

<ul class="cv-entry-list">
  {% for paper in conference_papers %}
    {% if paper.news_excerpt %}
      <li>
        <a href="{{ base_path }}{{ paper.url }}">{{ paper.title }}</a>
        <div class="cv-entry-detail">{{ paper.news_excerpt | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>
      </li>
    {% endif %}
  {% endfor %}
</ul>

Mentorship
======
* Mentored two interns at Yandex, Oleg Sorokin and Vladislav Dodonov. Both are now core developers on the RecSys R&D team (see, for example, [Gryphon](https://arxiv.org/abs/2606.08604)).

Grants
======

<ul class="cv-entry-list">
  {% for grant in grants %}
    <li>
      {% if grant.link %}<a href="{{ grant.link }}">{{ grant.title }}</a>{% else %}{{ grant.title }}{% endif %}
      <div class="cv-entry-detail">{{ grant.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>
    </li>
  {% endfor %}
</ul>

Technical Skills
======
* Languages:
  * Current: Python
  * Past: C/C++, Assembly, CUDA
* Frameworks:
  * Current: PyTorch
  * Past: TensorFlow, JAX