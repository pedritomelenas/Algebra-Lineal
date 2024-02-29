---
layout: page
title: Problemas resueltos
---
<style>
body {
  background-image: url('/public/logo_mda-net.svg');
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: 15% 15%;
  background-position: 100% 20%;
}
</style>

# Problemas resueltos

Por el momento, sólo ofrecemos problemas de los siguientes temas. La lista se irá ampliando hasta completar todos los contenidos de la asignatura.

{% for post in site.pages reversed %}
{% if post.tag=='problemas' %}
#### <a href="{{ post.url }}">{{ post.title }}</a>
{% endif %}
{% endfor %}
