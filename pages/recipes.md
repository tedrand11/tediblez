---
layout: page
title: Recipes
permalink: /recipes/
---

Browse home kitchen experiments, family bakes, and batch brews:

<!-- SVG Filter for Acid-Wash Liquid Bleach Warping -->
<svg style="position: absolute; width: 0; height: 0; overflow: hidden; pointer-events: none;" aria-hidden="true">
  <filter id="acid-wash-turbulence" x="0%" y="0%" width="100%" height="100%">
    <!-- Generates a soft liquid fractal noise map -->
    <feTurbulence 
      type="fractalNoise" 
      baseFrequency="0.015 0.03" 
      numOctaves="3" 
      result="noise" 
    />
    <!-- Smears and distorts the underlying gradient by 35px -->
    <feDisplacementMap 
      in="SourceGraphic" 
      in2="noise" 
      scale="35" 
      xChannelSelector="R" 
      yChannelSelector="G" 
    />
  </filter>
</svg>
<ul class="post-list recipe-feed-grid">
  {% for post in site.categories.recipes %}
    <li class="feed-card">
      <a class="feed-card-link" href="{{ post.url | relative_url }}">
        <!-- Post Cover Image Thumbnail -->
        {% if post.cover_image %}
          <div class="feed-thumbnail-wrapper">
            <img 
              src="{{ post.cover_image }}" 
              alt="{{ post.title | escape }}" 
              class="feed-thumbnail" 
              loading="lazy"
            />
          </div>
        {% else %}
          <!-- Optional fallback thumbnail if a post has no cover image -->
          <div class="feed-thumbnail-wrapper fallback-wrapper">
            <span class="fallback-text">Tediblez</span>
          </div>
        {% endif %}
        <!-- Post Content Details -->
        <div class="feed-card-content">
          <span class="post-meta">
            <span class="post-meta">
              {{ post.date | date: "%B %-d, %Y" }}
              {% if post.categories.first %}
                <span class="feed-category-tag">{{ post.categories.first }}</span>
              {% endif %}
            </span>
          </span>
          <h1 class="post-link-title">{{ post.title | escape }}</h1>
          {% if post.excerpt %}
            <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 22 }}</p>
          {% endif %}
        </div>
      </a>
    </li>
  {% endfor %}
</ul>