<!-- ---
layout: home
title: CloudOps
---
## Articles
 
 - [Optimizing Docker Images with Dive](/2025-03-23-docker-dive-guide) -->

---
layout: default
title: CloudOps
---

<h1 style="text-align: center; font-size: 2.5rem; color: #2c3e50;">🚀 CloudOps Blog</h1>
<p style="text-align: center; font-size: 1.2rem; color: #34495e;">Your go-to place for Cloud & DevOps insights!</p>

<hr>

<h2 style="color: #2980b9;">📝 Latest Post</h2>
{% for post in site.posts limit:1 %}
  <h3><a href="{{ post.url }}" style="color: #2980b9;">{{ post.title }}</a></h3>
  <p><strong>{{ post.date | date: "%B %d, %Y" }}</strong> - {{ post.excerpt }}</p>
  <a href="{{ post.url }}" style="color: #27ae60; text-decoration: none;">Read more →</a>
  <hr>
{% endfor %}

<h2 style="color: #8e44ad;">📚 All Posts</h2>
<ul style="list-style: none; padding: 0;">
{% for post in site.posts offset:1 %}
  <li style="margin-bottom: 10px;">
    <a href="{{ post.url }}" style="font-size: 1.2rem; color: #8e44ad; text-decoration: none;">
      {{ post.title }}
    </a> 
    <small style="color: #7f8c8d;">({{ post.date | date: "%B %d, %Y" }})</small>
  </li>
{% endfor %}
</ul>
