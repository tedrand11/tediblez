---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Home
---

<style>
  .hero-banner {
    text-align: center;
    padding: 2.5rem 1rem;
    background: #fdfaf6;
    border-radius: 12px;
    margin-bottom: 2.5rem;
    border: 1px solid #fae8d8;
  }
  .hero-banner h1 {
    font-size: 2.4rem;
    margin-bottom: 0.5rem;
    color: #2b2b2b;
  }
  .hero-banner p.tagline {
    font-size: 1.2rem;
    color: #666;
    margin-bottom: 1.5rem;
  }
  .btn-ig {
    display: inline-block;
    padding: 0.65rem 1.4rem;
    background-color: #d62976;
    background-image: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
    color: #fff !important;
    text-decoration: none;
    border-radius: 24px;
    font-weight: 600;
    font-size: 0.95rem;
  }
  .btn-ig:hover {
    opacity: 0.9;
  }
  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
    margin: 2rem 0;
  }
  .feature-card {
    padding: 1.5rem;
    border-radius: 8px;
    background: #fff;
    border: 1px solid #e1e4e8;
    text-align: center;
  }
  .feature-card h3 {
    margin-top: 0;
    margin-bottom: 0.5rem;
  }
  .coming-soon-banner {
    margin-top: 3rem;
    padding: 1.5rem;
    background: #f0f7f4;
    border-left: 4px solid #2e8555;
    border-radius: 4px;
  }
  .coming-soon-banner h3 {
    margin-top: 0;
    color: #205c3b;
    margin-bottom: 0.4rem;
  }
</style>

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
