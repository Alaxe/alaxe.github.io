---
layout: paper
title: fhelipe
date: 2024-06-24
full_title: >
  A Tensor Compiler with Automatic Data Packing for Simple
  and Efficient Fully Homomorphic Encryption
pdf: 
authors:
  - Aleksandar Krastev*
  - Nikola Samardzic*
  - Simon Langowski
  - Srinivas Devadas
  - Daniel Sanchez
equal_contribution: true
links:
  - title: Paper
    icon: file-pdf
    url: https://dl.acm.org/doi/pdf/10.1145/3656382
  - title: Code
    icon: github
    url: https://github.com/fhelipe-compiler/fhelipe
  - title: Talk
    icon: youtube
    url: https://www.youtube.com/live/CV2I0Ioyx7s?t=20880
  - title: Slides
    icon: chalkboard
    url: /assets/pdf/fhelipe_pldi24_slides.pdf
---
Fhelipe is an FHE compiler exposing an easy-to-use tensor programming interface.
Fhelipe simplifies programming by abstracting data layouts and noise management, while achieving great performance via two key contributions: a novel bit-permutation tensor layout representation and a novel bootstrap placement algorithm.
Fhelipe is the first compiler to match the performance of large hand-optimized FHE applications, outperforming prior compilers by gmean 18.5×.

I designed Fhelipe's layout representation, helped design all algorithms in the compiler, and implemented the compiler frontend.
