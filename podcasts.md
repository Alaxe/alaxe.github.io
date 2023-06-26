---
layout: default
permalink: /podcasts/
podcasts:
  - name: Good Starting Points
    shows:
    - name: Hello Internet
      href: https://www.hellointernet.fm/
    - name: Dear Hank and John
      href: https://complexly.com/shows/dear-hank-john
  - name: High-Volume
    shows:
    - name: Accidental Tech Podcast
      href: https://atp.fm/
    - name: Reconcilable Differences
      href: https://www.relay.fm/rd
    - name: The Unmade Podcast
      href: https://www.unmade.fm/
    - name: Do By Friday
      href: https://dobyfriday.com/
  - name: Low-Volume
    shows:
    - name: Cortex
      href: https://www.relay.fm/cortex
    - name: The Backmarkers
      href: https://www.relay.fm/backmarkers
    - name: Two Headed Girl
      href: https://twoheadedgirl.transistor.fm/
    - name: Robot or Not
      href: https://www.theincomparable.com/robot/
  - name: Scripted
    shows:
    - name: 99% Invisible
      href: https://99percentinvisible.org/
    - name: The Anthropocene Reviewed
      href: https://www.wnycstudios.org/podcasts/anthropocene-reviewed
---
# Podcasts I Like

{% for c in page.podcasts %}
  {{ c.name }}:
  <ul>
  {% for p in c.shows %}
    <li><a href="{{ p.href }}">{{ p.name }}</a></li>
  {% endfor %}
  </ul>
{% endfor %}
