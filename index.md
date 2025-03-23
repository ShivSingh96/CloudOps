<!-- ---
layout: home
title: CloudOps
---
## Articles
 
 - [Optimizing Docker Images with Dive](/2025-03-23-docker-dive-guide) -->
 ---
layout: home
title: "Welcome to CloudOps 🚀"
---

## 🌟 Featured Articles
- [Optimizing Docker Images with Dive](/2025-03-23-docker-dive-guide)

## 📝 Latest Posts
{% for post in site.posts limit:3 %}
- [{{ post.title }}]({{ post.url }}) <br> _Published on {{ post.date | date: "%B %d, %Y" }}_
{% endfor %}

---
👨‍💻 **CloudOps** is your go-to blog for Cloud & DevOps insights. Stay updated with the latest trends!
