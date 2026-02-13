---
layout: page
title: Listings
permalink: /listings/
---

<div class="container">
  <div class="listings-grid">

    {%- assign items = site.listings -%}
    {%- if items[0].order -%}
      {%- assign items = items | sort: "order" -%}
    {%- else -%}
      {%- assign items = items | sort: "date" -%}
      {%- assign items = items | reverse -%}
    {%- endif -%}

    {% for l in items %}
      <a class="listing-card" href="{{ l.url | relative_url }}">
        {% if l.hero %}
          <img src="{{ l.hero | relative_url }}" alt="{{ l.title }}">
        {% else %}
          <img src="{{ '/assets/images/hero.webp' | relative_url }}" alt="{{ l.title }}">
        {% endif %}

        <div class="listing-meta">
          {% if l.status %}<div class="listing-status">{{ l.status }}</div>{% endif %}
          <div class="listing-title">{{ l.title }}</div>
          {% if l.subtitle %}<div class="listing-sub">{{ l.subtitle }}</div>{% endif %}
          {% if l.description %}<div class="listing-sub">{{ l.description }}</div>{% endif %}
        </div>
      </a>
    {% endfor %}

  </div>
</div>
