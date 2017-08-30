---
layout: compress
title: Subscribe to Newsletter
description: Subscribe to newsletter to get the latest upates of Hasnain's blog right in your email.
---

<!DOCTYPE html>
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
     <form action="https://getsimpleform.com/messages?form_api_token=1b5bbc2f4b50b711d3d0bd6f4452f445" method="post">s
	  <!-- all your input fields here.... -->
	  <input type='text' name='test' />
	  <input type='submit' value='Test form' />
	</form>
    </div>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
