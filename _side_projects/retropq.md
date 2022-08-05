---
layout: side_project
title: "Retroactive Priority Queue"
code: https://github.com/6851-2021/retroactive-priority-queue
extra_links:
  - text: Original Paper
    icon: file-pdf
    href: http://erikdemaine.org/papers/Retroactive_TALG/paper.pdf
---
Class project for [6.851] (Advanced DS)
While a regular data structure supports only updates and queries to its latest
version, with a *retroactive* data structure it is possible to added or remove
operations at any point in a timeline.
The differ from *persistent* data structures in the sense that changes to the
past are propagated to the present (like in Back to the Future) instead of
creating a fork in the timeline.

This repository implements a *partially* retroactive priority queue: It supports
adding and removing priority queue updates (`insert` and `delete_min`) at any
point in the timeline but can perform queries only at the end of the timeline.
All operations are implemented in *logarithmic* time with respect to the length
of the timeline by using the data structure proposed in the [Retroactive Data
Structures][retro-ds] paper by Demaine, Iacono, and Langerman.


