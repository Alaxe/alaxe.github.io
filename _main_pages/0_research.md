---
layout: default
title: Research
permalink: /research/
---
# Research

I currently work on a hardware language that makes it easier to write pipelines with dependencies between operations (think an in-order core).
My approach is to provide language-level mechanisms that enable dependency-handling strategies (e.g., a register file with bypassing and stalling) to be implemented once and reused across different pipelines.
If doing a [UROP] on something related to this sounds interesting, feel free to reach out.

Previously, I worked with [Nikola Samardzic][nikola] on
accelerating Fully Homomorphic Encryption---encryption that allows running
programs on secret data without decrypting it.

{% assign papers = site.papers | sort: "date" | reverse %}
{% for paper in papers %}
  {{ paper.output }}
{% endfor %}

[urop]: https://urop.mit.edu/
[nikola]: https://n-samar.github.io/
