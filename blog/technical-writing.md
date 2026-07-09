---
layout: page
title: Technical Writing
permalink: /blog/technical-writing/
---

Thoughts on documentation best practices, API writing, AI tools 
for technical writers, and lessons learned from 20+ years in the 
field.

<a href="/blog/">← Back to Blog</a>

---

{% assign tw_posts = site.posts | where: "categories", 
"technical-writing" %}
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
