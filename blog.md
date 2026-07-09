---
layout: page
title: Blog
permalink: /blog/
---

Thoughts on technical writing, documentation best practices, 
AI tools, and the journey of building an aquascaping app from 
the ground up.

---

## ✍️ Technical Writing

Posts about documentation best practices, API writing, AI tools 
for technical writers, and lessons learned from 20+ years in the 
field.

{% assign tw_posts = site.posts | where: "categories", "technical-writing" %}
{% if tw_posts.size > 0 %}
{% for post in tw_posts %}
### [{{ post.title }}]({{ post.url }})
*{{ post.date | date: "%B %d, %Y" }}*

{{ post.excerpt }}

---
{% endfor %}
{% else %}
*No posts yet — check back soon.*
{% endif %}

---

## 🌿 Aquascape Vision

Updates on the development of my aquascaping app — design 
decisions, research findings, technical challenges, and lessons 
learned along the way.

{% assign av_posts = site.posts | where: "categories", "aquascape-vision" %}
{% if av_posts.size > 0 %}
{% for post in av_posts %}
### [{{ post.title }}]({{ post.url }})
*{{ post.date | date: "%B %d, %Y" }}*

{{ post.excerpt }}

---
{% endfor %}
{% else %}
*No posts yet — check back soon.*
{% endif %}
