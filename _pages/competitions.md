---
layout: archive
title: "Competitions & Olympiads"
permalink: /competitions/
author_profile: true
---

{% assign competitions = site.competitions | sort: "path" | reverse %}

{% for competition in competitions %}
<div class="list__item">
  <article class="archive__item" itemscope itemtype="http://schema.org/CreativeWork">
    <h2>
      {% if competition.link %}<a href="{{ competition.link }}">{{ competition.title }}</a>{% else %}{{ competition.title }}{% endif %}
    </h2>
    {% if competition.date_label %}<p class="page__meta"><i class="fa fa-clock" aria-hidden="true"></i> {{ competition.date_label }}</p>{% endif %}
    <p class="archive__item-excerpt" itemprop="description">
      {{ competition.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}
    </p>
  </article>
</div>
{% endfor %}
