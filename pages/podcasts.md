---
layout: default
permalink: /:basename/
title: Podcasts
podcasts:
  - name: Good Starting Points
    shows:
    - name: Hello Internet
      href: https://www.hellointernet.fm/66
    - name: Dear Hank and John
      href: https://complexly.com/shows/dear-hank-john
  - name: High-Volume
    shows:
    - name: Accidental Tech Podcast
      href: https://atp.fm/555
    - name: Reconcilable Differences
      href: https://www.relay.fm/rd/102
    - name: The Unmade Podcast
      href: https://www.unmade.fm/episodes/episode107
    - name: Do By Friday
      href: https://dobyfriday.com/episodes/324
  - name: Low-Volume
    shows:
    - name: Cortex
      href: https://www.relay.fm/cortex/91
    - name: The Adventure Zone
      href: https://maximumfun.org/podcasts/adventure-zone/
    - name: Robot or Not
      href: https://www.theincomparable.com/robot/142
    - name: Two Headed Girl
      href: https://twoheadedgirl.transistor.fm/7
    - name: The Backmarkers
      href: https://www.relay.fm/backmarkers
  - name: Retired
    shows:
    - name: You Look Nice Today
      href: https://www.youlooknicetoday.com/
    - name: California King
      href: https://www.californiaking.org/
    - name: The Anthropocene Reviewed
      href: https://www.wnycstudios.org/podcasts/anthropocene-reviewed/episodes/anthropocene-reviewed-hall-presidents-and-new-partner
    - name: Playing for Fun
      href: https://www.relay.fm/playingforfun
    - name: Ben, Ben and Blue
      href: https://www.youtube.com/@BenBenandBlue
    - name: The 3b1b podcast
      href: https://www.3blue1brown.com/podcast
    - name: Neutral
      href: https://neutral.fm/
    - name: Top Scallops
      href: https://topscallops.simplecast.com/
---
# Podcasts I Like

{% for c in page.podcasts %}
  {% include anchor-heading title=c.name level=3 %}
  <ul>
  {% for p in c.shows %}
    <li><a href="{{ p.href }}">{{ p.name }}</a></li>
  {% endfor %}
  </ul>
{% endfor %}
