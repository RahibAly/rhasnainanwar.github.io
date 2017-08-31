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
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; width:100%;}
	.button {
		background-color: #72cc96;
	}
	.about {
		border: none;
		width: 70%;
		margin: 20px auto;
	}
	.about td {
		padding-bottom: 15px;
    	text-align: center !important;
	}
	.about tr {
		font-size: 95%;
	}
	.center {
		margin: auto;
		text-align: center;
	}
</style>
<!-- Begin MailChimp Signup Form -->
<div class="center">
<link href="//cdn-images.mailchimp.com/embedcode/horizontal-slim-10_7.css" rel="stylesheet" type="text/css">
<div id="mc_embed_signup">
<form action="//github.us16.list-manage.com/subscribe/post?u=e4880a88dc03f9d0a411aa49d&amp;id=a78a932e57" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">Subscribe to my mailing list</label>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_e4880a88dc03f9d0a411aa49d_a78a932e57" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>
</div>
<!--End mc_embed_signup-->
<table class="about">
	<tr>
		<td>
			<a class="social-btn" href="/files/resume.pdf" target="_blank"><i class="fa fa-id-badge"> Résumé</i></a>
		</td>
		<td>
			<a class="social-btn" href="http://quora.com/profile/Raja-Hasnain-Anwar" target="_blank"><i class="fa fa-quora"> Read More</i></a>
		</td>
		<td>
			<a class="social-btn" href="/posts.html"><i class="fa fa-clipboard"> Posts</i></a>
		</td>
	</tr>
</table>
</div>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
