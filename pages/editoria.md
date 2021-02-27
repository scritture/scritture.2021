---
layout: page
title: editoria
permalink: /editoria/
description: escamontage
background: "/img/bg-post.jpg"
form: true
tipo: libro
---
## Escamontage
Fondata nel 2015, è una realtà editoriale indipendente non vincolata a linee predeterminate. Nata con l’intento di promuovere la cultura in ogni sua forma, utilizza le nuove tecnologie e le potenzialità del web per valorizzare l’importanza della pubblicazione cartacea.

Il catalogo annovera diverse collane, dal Magazine N°0 alle antologie, raccolte poetiche, romanzi, plaquette poetiche. I volumi sono presenti in fiere nazionali e internazionali. Le pubblicazioni sono curate da professionisti del settore in ogni aspetto, dall’impaginazione alla realizzazione, in collaborazione con artisti noti.

La divulgazione avviene attraverso eventi culturali e importanti librerie on-line che garantiscono la copertura a livello nazionale. Ogni pubblicazione è presente nel catalogo virtuale, la cui linkopedia viene costantemente aggiornata con recensioni, inviti alla lettura e il calendario delle presentazioni.

Una delle peculiarità di Edizioni EscaMontage è la presenza su diversi media come radio e siti web.

Vengono anche realizzati servizi aggiuntivi come la realizzazione di book-trailer, video interviste, etc. con preventivi personalizzati.

La pubblicazione è senza contributo da parte dell’autore!

Per informazioni inviare una e-mail a: [edizioni.escamontage@gmail.com](mailto:edizioni.escamontage@gmail.com)


Link al sito Festival Escamontage

[https://escamontage.wordpress.com](https://escamontage.wordpress.com)


Canale youtube di EscaMontage

[www.youtube.com/c/EscaMontage](https://www.youtube.com/c/EscaMontage/)



### Libri

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
  <p class="post-meta">
   {% include date.html  date=post.date %} 
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
