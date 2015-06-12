---
layout: page
title: Boş Bulunmuşluklarım
excerpt: "Boş zamanlar..."

image:
  feature: siirler.jpg
---

<ul class="post-list">
{% for post in site.categories.freetimes %} 
  <li><freetime><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d.%m.%y %H:%M:%S" }}</time></span></a></freetime></li>
{% endfor %}
</ul>
