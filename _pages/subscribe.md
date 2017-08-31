---
layout: compress
title: Subscribe to Newsletter
description: Subscribe to newsletter to get the latest upates of Hasnain's blog right in your email.
permalink: subscribe.html
---
<html>
{% include head.html %}
    
<body id="posts" class="inner-post-page">

	<div class="block-left">
	<div class="content">
	<a href="{{ site.url }}" class="logo"><img src="{{ site.url }}/images/{{ site.logo }}"></a>
	<div class="post-title-section">
		  <h1 class="section-title">{{ page.title | markdownify | remove: "<p>" | remove: "</p>" }}</h1>
		  <div class="section-line reverse"><a href="{{ site.url}}/posts">Back to posts</a> <em>/</em></div>
	</div>
	</div>
    </div>

<div class="block-right">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	.button {
		background-color: #72cc96;
	}
	.about {
	border: none;
	width: 100%;
	}
	.about td {
		padding-bottom: 15px;
    text-align: center !important;
	}
	.about tr {
		font-size: 95%;
	}
</style>
<table class="about">
	<tr>
	<td>
	<a class="social-btn" href="/files/resume.pdf" target="_blank">
	<i class="fa fa-id-badge"> Résumé</i>
	</a>
	</td>
	<td>
	<a class="social-btn" href="http://quora.com/profile/Raja-Hasnain-Anwar" target="_blank">
	<i class="fa fa-quora"> Read More</i>
	</a>
	</td>
	<td>
	<a class="social-btn" href="/subscribe.html">
	<i class="fa fa-paper-plane"> Subscribe</i>
	</a>
	</td>
	</tr>
</table>
</div>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
