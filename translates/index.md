---
layout: page
title: Çeviriler
excerpt: "Yaptığım Çeviriler"

image:
  feature: articles.png
---

<ul class="post-list">
{% for post in site.categories.translates %} 
  <li><translate><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span></a></translate></li>
{% endfor %}
</ul>
