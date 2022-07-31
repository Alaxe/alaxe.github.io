---
title: Research
layout: main_section
---
I'm primarily interested in *Computer Acrhitecture*---a thing about how you
organize computer hardware
Specialized hardware.
I work with Daniel and Nikola.
Most recently, I've worked on designing efficient accelerators for FHE

{% for paper in site.papers %}
  {{ paper.output }}
{% endfor %}
