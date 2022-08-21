---
title: Research
layout: main_section
---
I'm interested in computer architecture and improving performance through
specialized hardware.
My research so far has focused on accelerating Fully Homomorhpic
Encryption---encryption that allows running programs on secret data without
decrypting it.
Outside of architecture, I'm curious about systems more broadly (e.g.,
distributed system and compilers) and data structures.

I'm advised by Prof. [Daniel Sanchez][daniel] and working closely with
[Nikola Samardzic][nikola].

{% assign papers = site.papers | sort: "date" | reverse %}
{% for paper in papers %}
  {{ paper.output }}
{% endfor %}

[daniel]: https://people.csail.mit.edu/sanchez/
[nikola]: https://n-samar.github.io/
