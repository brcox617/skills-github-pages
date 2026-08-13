---
layout: default
title: Home
---

{% assign featured = site.posts | first %}

{% if featured %}
<section class="hero container">
  <article class="hero-card">
    <a href="{{ featured.url | relative_url }}">
      <img class="hero-image" src="{{ featured.image | default: '/assets/images/default-cover.svg' | relative_url }}" alt="{{ featured.title }}" />
      <h1 class="hero-title">{{ featured.title }}</h1>
    </a>
    <p class="hero-excerpt">{{ featured.excerpt | strip_html | truncate: 220 }}</p>
    <p class="post-meta">{{ featured.date | date: "%B %-d, %Y" }} • {{ featured.author }}</p>
  </article>
</section>
{% endif %}

<section class="posts container">
  <ul class="post-list">
    {% for post in site.posts offset:1 %}
    <li class="post-item">
      <a href="{{ post.url | relative_url }}">
        <img class="post-thumb" src="{{ post.image | default: '/assets/images/default-cover.svg' | relative_url }}" alt="{{ post.title }}" />
      </a>
      <div class="post-card-content" style="padding:0.75rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration:none;color:inherit;"><h3 class="post-title">{{ post.title }}</h3></a>
        <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</p>
        <p class="post-meta">{{ post.date | date: "%B %-d, %Y" }} • {{ post.author }}</p>
      </div>
    </li>
    {% endfor %}
  </ul>
</section>
