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
      {{ post.date | date_to_string }} <a href="{{ post.url }}">{{ post.title }}</a>
	  {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

<!-- <ul> -->
<!--   {% for post in site.posts %} -->
<!--     <li> -->
<!--       <h3><a href="{{ post.url }}">{{ post.date }}{{ post.title }}</a></h3> -->
<!--       {{ post.excerpt }} -->
<!--     </li> -->
<!--   {% endfor %} -->
<!-- </ul> -->

