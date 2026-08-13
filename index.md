---
layout: default
title: Home
---

# {{ site.title }}

{{ site.description }}

<ul class="post-list">
{% for post in site.posts %}
  <li class="post-item">
    <a href="{{ post.url | relative_url }}">
      <img class="post-thumb" src="{{ post.image | default: site.default_image | relative_url }}" alt="{{ post.title }}" />
      <h2 class="post-title">{{ post.title }}</h2>
    </a>
    <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
    <p class="post-meta">{{ post.date | date: "%B %-d, %Y" }}</p>
  </li>
{% endfor %}
</ul>
