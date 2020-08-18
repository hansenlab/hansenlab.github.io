---
layout: page
title : Blog
group: navigation
permalink: "blog.html"
---
{% include JB/setup %}

<ul>
{% assign posts_collate = site.posts %}
{% include JB/posts_collate %}
</ul>
