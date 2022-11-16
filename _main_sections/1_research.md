---
title: Research
layout: main_section
---
I'm interested in computer architecture research where I can apply
techniques from classical algorithms and data structure.
In particular, I'm interested in specialized hardware and hardware-software
co-design, as these subfields target the fundamental problem of maximizing
computation efficiency, without being limited by existing architectures.
I'm also curious about applying similar techniques outside of architecture more
broadly, for example in compilers or distributed systems.

So far, my research has focused on accelerating Fully Homomorphic
Encryption---encryption that allows running programs on secret data without
decrypting it.
I'm advised by Prof. [Daniel Sanchez][daniel] and have worked closely with
[Nikola Samardzic][nikola].

{% assign papers = site.papers | sort: "date" | reverse %}
{% for paper in papers %}
  {{ paper.output }}
{% endfor %}

[daniel]: https://people.csail.mit.edu/sanchez/
[nikola]: https://n-samar.github.io/
