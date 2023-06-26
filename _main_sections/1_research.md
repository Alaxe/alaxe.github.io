---
title: Research
layout: main_section
---
I want to do research in computer architecture where I apply techniques from
classical algorithms and data structures.
I'm not yet quite sure what this entails, but it will probably have something to
do with accelerators, compilers, and/or hardware-software co-design.
Ideally, I would be able to focus on maximizing efficiency, free from the
limitations of existing architectures.

During my undergrad, I collaborated closely with [Nikola Samardzic][nikola] on
accelerating Fully Homomorphic Encryption---encryption that allows running
programs on secret data without decrypting it.

{% assign papers = site.papers | sort: "date" | reverse %}
{% for paper in papers %}
  {{ paper.output }}
{% endfor %}

[nikola]: https://n-samar.github.io/
