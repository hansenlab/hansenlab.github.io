---
layout: page
title : Blog
group: navigation
permalink: "blog.html"
---
{% include JB/setup %}

<a href="http://feeds.feedburner.com/HansenLab" rel="alternate" type="application/rss+xml"><img src="//feedburner.google.com/fb/images/pub/feed-icon32x32.png" alt="" style="vertical-align:middle;border:0"/></a> <a href="http://feeds.feedburner.com/HansenLab" rel="alternate" type="application/rss+xml">Subscribe in a reader</a> 

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

