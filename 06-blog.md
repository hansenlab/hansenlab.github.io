---
layout: page
title : Blog
group: navigation
permalink: "blog.html"
---
{% include JB/setup %}

<a href="http://feeds.feedburner.com/HansenLab" rel="alternate"
      type="application/rss+xml"><img src="//feedburner.google.com/fb/images/pub/feed-icon32x32.png"
				      alt=""
				      style="vertical-align:middle;border:0"/></a>&nbsp;<a href="http://feeds.feedburner.com/HansenLab"
											   rel="alternate"
											   type="application/rss+xml">Subscribe</a>
<ul>
{% assign posts_collate = site.posts %}
{% include JB/posts_collate %}
</ul>
