---
layout: page
title : Blog
group: navigation
permalink: "blog.html"
---
{% include JB/setup %}

<p><div style="float:right">
<a href="http://feeds.feedburner.com/HansenLab" rel="alternate"
      type="application/rss+xml"><img src="//feedburner.google.com/fb/images/pub/feed-icon32x32.png"
				      alt=""
				      style="vertical-align:middle;border:0"/></a>&nbsp;<a href="http://feeds.feedburner.com/HansenLab"
											   rel="alternate"
											   type="application/rss+xml">Subscribe
    in a reader (All posts)</a>
<div style="height:5px;"></div>
<p><a href="http://feeds.feedburner.com/hansenlab/EjwS" title="Subscribe to my feed" rel="alternate"
   type="application/rss+xml"><img src="//feedburner.google.com/fb/images/pub/feed-icon32x32.png"
				   alt=""
				   style="border:0"/></a>&nbsp;<a href="http://feeds.feedburner.com/hansenlab/EjwS"
							    title="Subscribe to my feed"
							    rel="alternate"
							    type="application/rss+xml">Subscribe in
  a reader (R posts only)</a></div>

{% assign posts_collate = site.posts %}
{% include JB/posts_collate %}
