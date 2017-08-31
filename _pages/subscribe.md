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
     	<!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/horizontal-slim-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; width:80%; text-align: center;}
	.button {
		background-color: #72cc96;
	}
	.about {
	border: none;
	width: 100%;
}
.about td {
    padding-bottom: 20px;
    text-align: center !important;
}
.about tr {
	font-size: 95%;
}
section {
	width: 70%;
	margin: 0 auto;
}
</style>
<section>
<!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="//github.us16.list-manage.com/subscribe/post?u=e4880a88dc03f9d0a411aa49d&amp;id=a78a932e57" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<h2>Subscribe to our mailing list</h2>
<div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
<div class="mc-field-group">
	<label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
</label>
	<input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL">
</div>
	<div id="mce-responses" class="clear">
		<div class="response" id="mce-error-response" style="display:none"></div>
		<div class="response" id="mce-success-response" style="display:none"></div>
	</div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_e4880a88dc03f9d0a411aa49d_a78a932e57" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>
<script type='text/javascript' src='//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js'></script><script type='text/javascript'>(function($) {window.fnames = new Array(); window.ftypes = new Array();fnames[0]='EMAIL';ftypes[0]='email';fnames[1]='FNAME';ftypes[1]='text';fnames[2]='LNAME';ftypes[2]='text';fnames[3]='BIRTHDAY';ftypes[3]='birthday';}(jQuery));var $mcj = jQuery.noConflict(true);</script>
<!--End mc_embed_signup-->
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
</section>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
