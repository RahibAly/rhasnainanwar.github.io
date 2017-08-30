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
     	<form id="contact-form" class="form" action="https://getsimpleform.com/messages?form_api_token=1b5bbc2f4b50b711d3d0bd6f4452f445" method="POST">
        	<li class="contact-li">
            	<input type="email" placeholder="Your email" id="email" class="contact-input" name="email" tabindex="2">
            </li>
      		<input type="submit" value="Subscribe" id="submit">
    	</form>
    </div>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
