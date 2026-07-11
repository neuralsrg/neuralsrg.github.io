---
layout: archive
title: "Patents & Grants"
permalink: /patents/
author_profile: true
---

<h2>Patents</h2><hr />

{% assign patents = site.patents | sort: "path" | reverse %}

{% for patent in patents %}
<div class="list__item">
  <article class="archive__item" itemscope itemtype="http://schema.org/CreativeWork">
    <h2 class="archive__item-title" itemprop="headline">
      {% if patent.link %}<a href="{{ patent.link }}">{{ patent.title }}</a>{% else %}{{ patent.title }}{% endif %}
    </h2>
    {% if patent.date_label %}<p class="page__meta"><i class="fa fa-clock" aria-hidden="true"></i> {{ patent.date_label }}</p>{% endif %}
    <p class="archive__item-excerpt" itemprop="description">
      {{ patent.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}
    </p>
  </article>
</div>
{% endfor %}

<h2>Grants</h2><hr />

{% assign grants = site.grants | sort: "path" | reverse %}

{% for grant in grants %}
<div class="list__item">
  <article class="archive__item" itemscope itemtype="http://schema.org/CreativeWork">
    <h2>
      {% if grant.link %}<a href="{{ grant.link }}">{{ grant.title }}</a>{% else %}{{ grant.title }}{% endif %}
    </h2>
    {% if grant.date_label %}<p class="page__meta"><i class="fa fa-clock" aria-hidden="true"></i> {{ grant.date_label }}</p>{% endif %}
    <p class="archive__item-excerpt" itemprop="description">
      {{ grant.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}
    </p>
  </article>
</div>
{% endfor %}
