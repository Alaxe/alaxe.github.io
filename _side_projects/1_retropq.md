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
(here, `insert` and `delete_min`) on past versions of the data structure.
Retroactive differs from persistent in that the effects of changing past
operations propagate to the present (like in *Back to the Future*).
I implemented the data structure proposed by Demaine, Iacono, and Langerman,
which performs all operations in *logarithmic* time.

