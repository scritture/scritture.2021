---
layout: page
title: cronache
permalink: /cronache/
description: Frascati
background: '/img/posts/04.jpg'
tipo: cronache
---




{% for post in site.posts  %}
  {% if post.tipo == page.tipo %}
<article class="post-preview">
  <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h3 class="post-subtitle">{{ post.subtitle }}</h3>
    {% else %}
    <h3 class="post-subtitle">{{ post.excerpt | strip_html | truncatewords: 15 }}</h3>
    {% endif %}
  </a>
  <p class="post-meta">{{posted_by}}
    {% if post.author %}
    {{ post.author }}
    {% else %}
    {{ site.author }}
    {% endif %}
    &middot;  {% include date.html  date=post.date %} 
  </p>
</article>

<hr>
    {% endif %}
{% endfor %}

<!-- Pager -->
{% if paginator.total_pages > 1 %}

<div class="clearfix">

  {% if paginator.previous_page %}
  <a class="btn btn-primary float-left" href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr;
    Newer<span class="d-none d-md-inline"> Posts</span></a>
  {% endif %}

  {% if paginator.next_page %}
  <a class="btn btn-primary float-right" href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older<span class="d-none d-md-inline"> Posts</span> &rarr;</a>
  {% endif %}

</div>

{% endif %}