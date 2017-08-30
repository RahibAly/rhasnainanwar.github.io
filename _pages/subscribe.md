---
layout: compress
title: Subscribe to Newsletter
description: Subscribe to newsletter to get the latest upates of Hasnain's blog right in your email.
permalink: subscribe.html
---
<html>
{% include head.html %}
<style>
	#contact-form {
  		padding: 10px;
		border: 1px solid #4dbe7a;
		top: 45%;
	}
	#submit{
		 display: inline-block;
		 background: transparent;
		 border: 1px solid #4dbe7a;
		 padding: 2px 10px;
		
	}
	li.contact-li {
		list-style: none;
		padding: 0;
		display: inline-block;
	}

	.contact-input{
	  outline:none;
	  border: none;
	  border-bottom: 1px solid #4dbe7a;
	  
	}
</style>
    
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
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; width:100%;}
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
	<div id="mc_embed_signup">
	<form action="//github.us16.list-manage.com/subscribe/post?u=e4880a88dc03f9d0a411aa49d&amp;id=cce8de2da7" method="post" id="mc-embedded-subscribe-form contact-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">Subscribe to our mailing list</label>
	<li class="contact-li">
	<input type="email" value="" name="EMAIL" class="email contact-input" id="mce-EMAIL" placeholder="email address" required>
	</li>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_e4880a88dc03f9d0a411aa49d_cce8de2da7" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe submit" class="button"></div>
    </div>
</form>
</div>

<!--End mc_embed_signup-->
    </div>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
