---
layout: page
title: Recipes
permalink: /recipes/
---

Browse home kitchen experiments, family bakes, and batch brews:

<ul class="post-list">
  {% for post in site.categories.recipes %}
    <li>
      {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
      <span class="post-meta">{{ post.date | date: date_format }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      {% if post.excerpt %}
        {{ post.excerpt }}
      {% endif %}
    </li>
  {% else %}
    <p>No recipes published yet. Check back soon!</p>
  {% endfor %}
</ul>