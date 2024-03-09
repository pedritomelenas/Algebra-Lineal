---
layout: page
title: Problemas resueltos
---

# Problemas resueltos

Por el momento, sólo ofrecemos problemas de los siguientes temas. La lista se irá ampliando hasta completar todos los contenidos de la asignatura.

{% for post in site.pages %}
{% if post.tag=='problemas' %}
#### <a href="{{ post.url }}">{{ post.title }}</a>
{% endif %}
{% endfor %}
