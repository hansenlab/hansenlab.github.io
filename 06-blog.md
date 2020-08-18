---
layout: page
title : Blog
group: navigation
permalink: "blog.html"
---
{% include JB/setup %}

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

