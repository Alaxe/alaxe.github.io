---
layout: main_section
---
These are some things I've worked on in high sschool.

{% for project in site.side_projects %}
  {{ project.output }}
{% endfor %}
