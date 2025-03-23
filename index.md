---
layout: default
title: CloudOps Blog
---

<h1 style="text-align: center; font-size: 2.5rem; color: #2c3e50;">🚀 CloudOps Blog</h1>
<p style="text-align: center; font-size: 1.2rem; color: #34495e;">Your go-to place for Cloud & DevOps insights!</p>

<hr>

<!-- Display Latest Post in Highlighted Style -->
<h2 style="color: #2980b9;">📄 Latest Post</h2>
{% if site.posts.size > 0 %}
  {% assign latest_post = site.posts | first %}
  <div style="background: #f8f9fa; padding: 15px; border-radius: 10px; margin-bottom: 20px;">
    <h3><a href="{{ site.baseurl }}{{ latest_post.url }}" style="color: #2980b9;">{{ latest_post.title }}</a></h3>
    <p><strong>{{ latest_post.date | date: "%B %d, %Y" }}</strong></p>
    <p>{{ latest_post.excerpt }}</p>
    <a href="{{ site.baseurl }}{{ latest_post.url }}" style="color: #27ae60;">Read more →</a>
  </div>
{% else %}
  <p>No blog posts yet. Stay tuned!</p>
{% endif %}

<!-- List Older Posts -->
{% if site.posts.size > 1 %}
  <h2 style="color: #8e44ad;">📚 More Posts</h2>
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
{% endif %}

<!-- Custom Footer -->
<footer style="text-align: center; margin-top: 50px; padding: 20px; background: #2c3e50; color: #ecf0f1; border-radius: 10px;">
  <p style="margin: 0; font-size: 1rem;">© 2025 CloudOps | All rights reserved.</p>
  <p style="margin: 5px 0 0; font-size: 0.9rem;">Follow us for the latest updates on Cloud & DevOps!</p>
</footer>
