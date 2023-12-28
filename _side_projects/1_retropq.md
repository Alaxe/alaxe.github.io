---
title: Retroactive Priority Queue
links:
  - title: Code
    icon: github
    url: https://github.com/6851-2021/retroactive-priority-queue
  - title: Original Paper
    icon: file-pdf
    url: http://erikdemaine.org/papers/Retroactive_TALG/paper.pdf
---
A priority queue that supports adding and removing updates (`insert` and
`delete_min`) on past versions of the data structure.
Retroactivity differs from persistence in that the effects of changing past
operations propagate to the present (think, _Back to the Future_).
I implemented the data structure proposed by Demaine, Iacono, and Langerman,
which performs all operations in _logarithmic_ time.

