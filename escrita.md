---
layout: page
title: Escrita
permalink: /escrita/
---

Três textos de novembro de 2015, sobre qualidade de software e testes
unitários. Ficaram parados desde então — mas continuam valendo, e a URL de cada
um é a mesma de sempre.

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-meta">{% include data-pt.html data=post.date %}</span>
      <h2><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    </li>
  {% endfor %}
</ul>

<p class="rss-subscribe">Se algum dia voltarem a aparecer:
<a href="{{ '/feed.xml' | relative_url }}">feed RSS</a>.</p>
