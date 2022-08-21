---
title: Side Projects
layout: main_section
---
{% for project in site.side_projects %}
  {{ project.output }}
{% endfor %}
