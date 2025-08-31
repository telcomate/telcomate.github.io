---
layout: home
title: Welcome
---

# Welcome to Our Blog

This is the home page of our Jekyll blog hosted on GitHub Pages.

Check out our latest posts below!

<h1>Posts</h1>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <small>{{ post.date | date: "%Y-%m-%d" }}</small>
    </li>
  {% endfor %}
</ul>
