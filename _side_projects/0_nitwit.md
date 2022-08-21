---
layout: side_project
title: Nitwit
links:
  - text: Code
    icon: github
    href: https://github.com/Alaxe/nitwit
  - text: Docs
    icon: book
    href: https://github.com/Alaxe/nitwit/blob/master/docs/spec.md
---
I made up a programming language that uses [prefix notation] for amusement
purposes: for example, `a = (b + c) * d` looks like `= a * + b c d`.
Nitwit is imperative, strongly typed, and uses reference counting garbage
collection.
The Nitwit compiler procudes C code, which can then be compiled to an
executable.

[prefix notation]: https://en.wikipedia.org/wiki/Polish_notation
