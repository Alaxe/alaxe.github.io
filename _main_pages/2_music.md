---
layout: default
title: Music
permalink: /music/
---
# Music
As I took some music classes at MIT, I ended up composing a couple of short pieces.
Here are the ones that turned out okay.

Most recordings are computer-generated.

{% for music in site.music %}
  {{ music.output }}
{% endfor %}

