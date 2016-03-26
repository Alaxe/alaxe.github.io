---
layout: page
title: About
permalink: /about/
---
 - Name: Alexander "Perchema" Crustev
 - Born: 9th of June 2000
 - Location: Varna, Bulgaria
 - Contact: <aleks.tcr@gmail.com>
 - Github: [Alaxe][gh-prof]
 - Codeforces: [Perchema][cf-prof]

## Projects
While there are a lot of small tech demos / experiments I've developed, there're 
only a few, which are worth showing.

 - ### [JudgeSystem][judgesystem-deploy]
   This is a web-based system for grading solutions to algorithmic problems. I.
   e. You submit your code (C/C++), it gets compiled, run on some unit tests 
   and you get feedback on which tests have passed successfully. It supports
   time limits, memory limits, and custom output checkers. It uses Django in 
   the backend with Celery as a task queue and Bootstrap (a bit modified) for
   the CSS. Code is on [Github][judgesystem-repo].

   *The link in the title may not always load, since it's curently hosted on my
   computer*
 - ### [Stealth][stealth-deploy]
   This is *(Who would have guessed ?)* a stealth game written in javascript.
   In short: you have to steal some coins from the level, while not being
   spotted by the guards. The algorithm used for the lighting / guard detection
   is quite interesting and I may explain it in a future blog. The game has been
   made using [Phaser][phaser] as a framework  and [Tiled][tiled] as a level 
   editor. Code is on [Github][stealth-repo].
 - ### [ChochoRun][chocho-deploy]
   This is a kind of simple runner with procedural level generation. You're a
   panda collecting small bamboo sticks while avoiding big ones. It gets faster
   and faster so you eventually die and get a score. This project is written in
   java using [Libgdx][libgdx] - a library letting you deploy your game on
   multiple platforms. I've recently uploaded the source on
   [Github][chocho-repo].

[gh-prof]: https://github.com/Alaxe/ "Github profile"
[cf-prof]: http://codeforces.com/profile/perchema/ "Codeforces profile"

[judgesystem-deploy]: https://judgesystem.tk/ "Judge system"
[judgesystem-repo]: https://github.com/Alaxe/judgeSystem/ "Judge system repo"

[stealth-deploy]: http://perchema.tk/stealth/
[stealth-repo]: https://github.com/Alaxe/stealth/
[phaser]: http://phaser.io/
[tiled]: http://www.mapeditor.org/

[chocho-deploy]: http://perchema.tk/ChochoRun/
[chocho-repo]: http://github.com/Alaxe/ChochoRun/
[libgdx]: https://libgdx.badlogicgames.com/
