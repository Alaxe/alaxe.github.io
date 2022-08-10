---
layout: default
permalink: /podcasts/
podcasts:
  - name: Accidental Tech Podcast
    href: https://atp.fm/
  - name: Do By Friday
    href: https://dobyfriday.com/
  - name: Cortex
    href: https://www.relay.fm/cortex
  - name: Reconcilable Differences
    href: https://www.relay.fm/rd
  - name: The Backmarkers
    href: https://www.relay.fm/backmarkers
  - name: The Unmade Podcast
    href: https://www.unmade.fm/
  - name: Dear Hank and John
    href: https://complexly.com/shows/dear-hank-john
  - name: Two Headed Girl
    href: https://twoheadedgirl.transistor.fm/
  - name: Under the Radar
    href: https://www.relay.fm/radar
  - name: Robot or Not
    href: https://www.theincomparable.com/robot/
  - name: Hello Internet
    href: https://www.hellointernet.fm/
---
# Podcasts I Like

<ul>
{% for p in page.podcasts %}
  <li><a href="{{ p.href }}">{{ p.name }}</a></li>
{% endfor %}
</ul>
