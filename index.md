---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Home
---

<div class="hero-banner">
  <div class="hero-brand">
    <h1>Tediblez Bay Area</h1>
    <p class="tagline">Crafting flavor, community, and experiences across the Bay.</p>
  </div>

  <a class="ig-profile-card" href="https://www.instagram.com/tediblez_bayarea/" target="_blank" rel="noopener noreferrer">
    <!-- Profile Thumbnail with Instagram Gradient Ring -->
    <div class="ig-avatar-ring">
      <img 
        src="https://res.cloudinary.com/q0j7dwxf/image/upload/v1793776734/1793776673156.jpg" 
        alt="@tediblez_bayarea" 
        class="ig-avatar-img"
        loading="lazy"
      />
    </div>
    <div class="ig-profile-details">
      <span class="ig-handle">@tediblez_bayarea</span>
      <span class="ig-action">Follow on Instagram &rarr;</span>
    </div>
  </a>
</div>

---

<ul class="post-list recipe-feed-grid">
  {% for post in site.posts %}
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
            {% if post.categories.first %}
              <span class="feed-category-tag">{{ post.categories.first }}</span>
            {% endif %}
          </span>
          <h2 class="post-link-title">{{ post.title | escape }}</h2>
          {% if post.excerpt %}
            <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 22 }}</p>
          {% endif %}
        </div>
      </a>
    </li>
  {% endfor %}
</ul>

<div class="coming-soon-banner">
  <h3>✨ More Tediblez Blog Content Coming Soon</h3>
  <p>
    We're currently writing behind-the-scenes stories, recipes, local Bay Area highlights, and flavor drops. 
    In the meantime, head over to 
    <a href="https://www.instagram.com/tediblez_bayarea/" target="_blank" rel="noopener noreferrer">@tediblez_bayarea</a> 
    to catch all the latest updates and announcements.
  </p>
</div>
