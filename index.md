---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Home
---

<div class="hero-banner">
  <h1>Tediblez Bay Area</h1>
  <p class="tagline">Crafting flavor, community, and experiences across the Bay.</p>
  <a class="btn-ig" href="https://www.instagram.com/tediblez_bayarea/" target="_blank" rel="noopener noreferrer">
    Follow @tediblez_bayarea on Instagram
  </a>
</div>

---

{% if site.posts.size > 0 %}
  <h2 class="post-list-heading">Latest Posts</h2>
  <ul class="post-list">
    {% for post in site.posts limit:5 %}
      <li>
        {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {% if site.show_excerpts %}
          {{ post.excerpt }}
        {% endif %}
      </li>
    {% endfor %}
  </ul>
{% endif %}

<div class="coming-soon-banner">
  <h3>✨ The Tediblez Blog is Coming Soon</h3>
  <p>
    We're currently writing behind-the-scenes stories, recipes, local Bay Area highlights, and flavor drops. 
    In the meantime, head over to 
    <a href="https://www.instagram.com/tediblez_bayarea/" target="_blank" rel="noopener noreferrer">@tediblez_bayarea</a> 
    to catch all the latest updates and announcements.
  </p>
</div>
