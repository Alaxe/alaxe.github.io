---
title: Research
layout: main_section
---
I'm interested in *computer architecture* and improving application performance
through specialized hardware.
My research so far has focused on accelerating Fully Homomorhpic
Encryption---encryption that allows running programs on secret data without
decrypting it.
Outside of architecture, I'm curious about systems more in general (e.g.,
distributed system and compilers) and in data structures.

I'm been advised by Prof. [Daniel Sanchez][daniel] and I'm working closely with
[Nikola Samardzic][nikola].


{% for paper in site.papers %}
  {{ paper.output }}
{% endfor %}

[daniel]: https://people.csail.mit.edu/sanchez/
[nikola]: https://n-samar.github.io/
