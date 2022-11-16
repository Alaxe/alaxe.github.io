---
layout: paper
title: CraterLake
date: 2022-06-01
full_title: >
  CraterLake: A Hardware Accelerator for Efficient Unbounded Computation on
  Encrypted Data
pdf: https://dl.acm.org/doi/pdf/10.1145/3470496.3527393
authors:
  - Nikola Samardzic
  - Axel Feldmann
  - Aleksandar Krastev
  - Nathan Manohar
  - Nicholas Genise
  - Srinivas Devadas
  - Karim Eldefrawy
  - Chris Peikert
  - Daniel Sanchez
links:
  - text: Paper
    icon: file-pdf
    href: https://dl.acm.org/doi/pdf/10.1145/3470496.3527393
---
CraterLake is the state-of-the-art hardware accelerator for FHE, providing
speedups of 5,000× over CPU on a broad range of applications.
Building upon F1's functional units, CraterLake introduces a novel architecture
that significantly reduces on- and off-chip data movement.

I came up with the way computation is distributed across the chip (Sec. 4),
designed the on-chip network (Sec. 5.3), and designed the KeySwitch hint
generator (Sec. 5.2).
