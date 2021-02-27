---
layout: diario
title: diario
permalink: /diario/
description: di Claudio Comandini
background: '/img/bg-index.jpg'
author: "Claudio Comandini"
---



{% for post in site.posts  %}
  {% if post.author == page.author %}
<article class="post-preview">
<div class="row">
<div class="col-lg-3 col-md-3 ">
        {% if post.image %}
        <img src="{{post.image}}" class="img-fluid" alt="">
        {% endif %}
</div>
<div class="col-lg-9 col-md-9 mx-auto">
  <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h3 class="post-subtitle">{{ post.subtitle }}</h3>
    {% else %}
    <p class="post-subtitle">{{ post.excerpt | strip_html | truncatewords: 15 }}</p>
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
  </div>
</div>

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
