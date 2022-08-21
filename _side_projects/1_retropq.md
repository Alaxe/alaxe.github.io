---
layout: side_project
title: Retroactive Priority Queue
links:
  - text: Code
    icon: github
    href: https://github.com/6851-2021/retroactive-priority-queue
  - text: Original Paper
    icon: file-pdf
    href: http://erikdemaine.org/papers/Retroactive_TALG/paper.pdf
---
A partially *retroactive* priority queue supports adding and removing updates
(here, `insert` and `delete_min`) on past versions of the data structure, with
the effects of these operations propagating to the present (think
Back to the Future, not persistent data structures).
I implemented the data structure proposed by Demaine, Iacono, and Langerman,
which performs all operations in *logarithmic* time.

