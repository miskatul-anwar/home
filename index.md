---
layout: default
title: Home
---

<section class="hero">
  <h1>Welcome</h1>
  <p>Small posts in a clean grid layout, with a simple tab bar on top.</p>
</section>

<section class="post-grid">
  {% for post in site.posts limit: 9 %}
    <article class="post-card">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</div>
      <div class="post-excerpt">
        {{ post.excerpt | strip_html | truncate: 140 }}
      </div>
    </article>
  {% endfor %}
</section>

{% if site.posts == empty %}
<p>No posts yet. Add files to <code>_posts/</code> to populate the grid.</p>
{% endif %}
