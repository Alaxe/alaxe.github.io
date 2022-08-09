---
layout: side_project
code: https://github.com/Alaxe/nitwit
extra_links:
  - text: Docs
    icon: book
    href: https://github.com/Alaxe/nitwit/blob/master/docs/spec.md
---
I made up a programming language that uses [prefix notation] for
amusement purposes (for example, `a = (b + c) * d` looks like `= a * + b c d`).
Nitwit is imperative, strongly typed, and uses reference counting garbage
collection.
I implemented a compiler that translates Nitwit code to C, which can then be
compiled to an executable.

[prefix notation]: https://en.wikipedia.org/wiki/Polish_notation
