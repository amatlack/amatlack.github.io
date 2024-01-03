---
layout: page
permalink: /categories/
title: Categories
---


<div id="archives">
{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    
  <h2 style="text-align:left;">{{ category_name }}</h2>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <ul class="past">
      <p><b><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></b>
      </p>
      </ul>
    </article>
    {% endfor %}
  </div>
{% endfor %}
    <div class="archive_footer">
    <p>If you prefer, you can also view <a href="{{ site.baseurl }}/posts">posts organized chronologically</a>.</p>
    </div>
</div>
