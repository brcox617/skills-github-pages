---
layout: default
title: Home
---

# {{ site.title }}

{{ site.description }}

<ul class="post-list">
{% raw %}{% for post in site.posts %}{% endraw %}
  <li class="post-item">
    <a href="{% raw %}{{ post.url }}{% endraw %}">
      <img class="post-thumb" src="{% raw %}{{ post.image | default: site.defaults[0].values.image }}{% endraw %}" alt="{% raw %}{{ post.title }}{% endraw %}" />
      <h2 class="post-title">{% raw %}{{ post.title }}{% endraw %}</h2>
    </a>
    <p class="post-excerpt">{% raw %}{{ post.excerpt | strip_html | truncate: 160 }}{% endraw %}</p>
    <p class="post-meta">{% raw %}{{ post.date | date: "%B %-d, %Y" }}{% endraw %}</p>
  </li>
{% raw %}{% endfor %}{% endraw %}
</ul>
