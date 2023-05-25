---
layout: main_section
title: Classes I've Taken
now: Summer 2023
---
{% for cat in site.data.classes %}
  <details>
    <summary>
      {{ cat.category }}
    </summary>
    <table>
      <thead>
        <tr>
          <th>#</th>
          <th>Name</th>
          <th>Term</th>
        </tr>
      </thead>
      <tbody>
        {% for cl in cat.classes %}
          <tr>
            <td class="course">{{ cl.number }}</td>
            <td>{{ cl.name }}</td>
            <td class="course">
              {% if cl.semester == "ASE" %}
                <span data-tooltip="Advanced Standing Exam">ASE</span>
              {% elsif cl.semester == page.now %}
                <em>{{ cl.semester }}</em>
              {% else %}
                {{ cl.semester }}
              {% endif %}
            </td>
          </tr>
        {% endfor %}
      </tbody>
    </table>
  </details>
{% endfor %}
