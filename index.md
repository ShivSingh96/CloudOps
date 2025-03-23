---
layout: default
title: CloudOps
---

<h1 style="text-align: center; font-size: 2.5rem; color: #2c3e50;">🚀 CloudOps Blog</h1>
<p style="text-align: center; font-size: 1.2rem; color: #34495e;">Your go-to place for Cloud & DevOps insights!</p>

<hr>

<h2 style="color: #2980b9;">📄 Latest Post</h2>
{% for post in site.posts limit:1 %}
  <div style="background: #f8f9fa; padding: 15px; border-radius: 10px; margin-bottom: 20px;">
    <h3><a href="{{ site.baseurl }}{{ post.url }}" style="color: #2980b9;">{{ post.title }}</a></h3>
    <p><strong>{{ post.date | date: "%B %d, %Y" }}</strong></p>
    <p>{{ post.excerpt }}</p>
    <a href="{{ site.baseurl }}{{ post.url }}" style="color: #27ae60;">Read more →</a>
  </div>
{% endfor %}

<h2 style="color: #8e44ad;">📚 All Posts</h2>
<ul style="list-style: none; padding: 0;">
{% for post in site.posts offset:1 %}
  <li style="margin-bottom: 10px;">
    <a href="{{ site.baseurl }}{{ post.url }}" style="font-size: 1.2rem; color: #8e44ad;">
      {{ post.title }}
    </a> 
    <small style="color: #7f8c8d;">({{ post.date | date: "%B %d, %Y" }})</small>
  </li>
{% endfor %}
</ul>
