---
layout: side_project
title: "Retroactive Priority Queue"
code: https://github.com/6851-2021/retroactive-priority-queue
extra_links:
  - text: Original Paper
    icon: file-pdf
    href: http://erikdemaine.org/papers/Retroactive_TALG/paper.pdf
---
I implemented a (partially) *retroactive* priority queue: it supports adding and
removing updates (`insert` and `delete_min`) on past versions of the data
structure, with the effects of these operations propagating to the present (like in
Back to the Future, unlike persistent data structures).
Using the data structure by Demaine, Iacono, and Langerman, all operations
still work in *logarithmic* time.


