---
layout: default
title: ""
links:
  - title: Github
    icon: github
    url: https://github.com/Alaxe
  - title: alexalex@mit.edu
    icon: envelope
    url: mailto:alexalex@mit.edu
  - title: Resume
    icon: business-time
    url: /resume/aleksandar-krastev.pdf
---
# Hello There!

I'm <span id="a">a</span> PhD student doing research in computer architecture and programming languages.
I work with Professor [Daniel Sanchez][Daniel].

Besides that, I enjoy listening to [podcasts], [tinkering][Linux] with Linux, and most recently, fixing up an [80's Schwinn Le Tour][Schwinn].

[daniel]: https://people.csail.mit.edu/sanchez/
[podcasts]: /podcasts
[linux]: https://github.com/Alaxe/configs
[schwinn]: /assets/schwinn.jpg

{% include links links=page.links%}

<script>
  let year = (new Date()).getFullYear();
  let month = (new Date()).getMonth();
  let i = year - 2024 + (month >= 9);

  const ord = ["first", "second", "third", "fourth", "fifth", "sixth", "seventh"];
  let alt_text = (i in ord) ? `${ord[i]}-year` : "late-stage";
  document.getElementById("a").title = alt_text;
</script>
