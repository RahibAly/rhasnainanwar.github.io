---
layout: compress
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
          <ul class="tags">
            {% for tag in page.tags %}
              <li><a href="{{ site.url }}/tags#{{ tag }}">{{ tag }}</a></li>
              {% unless forloop.last %}
              {% endunless %}
            {% endfor %}
          </ul>
          <div class="section-line reverse"><a href="{{ site.url}}/posts">Back to posts</a> <em>/</em></div>
        </div>
      </div>
    </div>

    <div class="block-right">
     <form action="https://getsimpleform.com/messages?form_api_token=1b5bbc2f4b50b711d3d0bd6f4452f445" method="post">
  <!-- the redirect_to is optional, the form will redirect to the referrer on submission -->
  <input type='hidden' name='redirect_to' value='<the complete return url e.g. http://fooey.com/thank-you.html>' />
  <!-- all your input fields here.... -->
  <input type='text' name='test' />
  <input type='submit' value='Test form' />
</form>
    </div>
    {% include scripts.html %}
    {% include overlay.html %}
</body>
</html>
