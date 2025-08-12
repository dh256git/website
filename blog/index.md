---
title: Blog
layout: default
---

# Blog

{% assign posts = site.posts %}
{% for post in posts %}
- <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  <time datetime="{{ post.date | date_to_xmlschema }}">({{ post.date | date: "%Y-%m-%d" }})</time>
{% endfor %}
