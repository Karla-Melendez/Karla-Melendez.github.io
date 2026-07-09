---
layout: page
title: Aquascape Vision
permalink: /blog/aquascape-vision/
---

Updates on the development of my aquascaping app — design 
decisions, research findings, technical challenges, and lessons 
learned along the way.

<a href="/blog/">← Back to Blog</a>

---

{% assign av_posts = site.posts | where: "categories", 
"aquascape-vision" %}
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
