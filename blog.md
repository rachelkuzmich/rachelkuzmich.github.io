---
layout: default
title: Blog
permalink: /blog/
---

# Blog

<ul>
{% for post in site.posts %}
  <li style="margin-bottom: 2em;">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p><em>{{ post.date | date: "%b %-d, %Y" }}</em></p>
    <p>{{ post.excerpt | strip_html | truncate: 200 }}</p>
    <p><a href="{{ post.url | relative_url }}">Read more →</a></p>
  </li>
{% endfor %}
</ul>

