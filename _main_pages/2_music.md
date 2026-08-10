---
layout: default
title: Music
permalink: /music/
---
# Music
I wrote a few short pieces for classes in college.
Here are the ones I'm happy with:

{% for music in site.music %}
  {{ music.output }}
{% endfor %}

