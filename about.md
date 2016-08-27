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
 - [IOI stats][ioi-stats]

## Projects
While there are a lot of small tech demos / experiments I've developed, there're 
only a few, which are worth showing.

 - ### [JudgeSystem][judgesystem-deploy]
   A web-based system for grading solutions to algorithmic problems. I.
   e. You submit your code (C/C++), it gets compiled, ran on some unit tests 
   and you get feedback on which tests have passed successfully. It supports
   time limits, memory limits, and custom output checkers. It uses Django in 
   the backend with Celery as a task queue and Bootstrap (a bit modified) for
   the CSS. Code is on [Github][judgesystem-repo].

 - ### [Stealth][stealth-deploy]
   A stealth game written in javascript. In short: you have to steal some coins 
   from the level, while not being spotted by the guards. The algorithm used for
   the lighting / guard detection is quite interesting and I might explain it in
   a future blog. The game has been made using [Phaser][phaser] as the framework 
   and [Tiled][tiled] as the level editor. Code is on [Github][stealth-repo].

 - ### [ChochoRun][chocho-deploy]
   A kind of simple runner game with procedural level generation. You're 
   a panda collecting small bamboo sticks while avoiding big ones. You move
   faster and faster so you eventually die and get a score. This project is 
   written in java using [Libgdx][libgdx] - a library letting you deploy your
   game on multiple platforms. I've recently uploaded the source on
   [Github][chocho-repo].

 - ### [Between Worlds][between-deploy]
   A game where you have to run through a maze, but with a twist - there
   are two "worlds" (or layers), connected by portals. To beat the level the 
   player has to constantly switch between the worlds and even activate some of 
   the portals. Each time you face a bigger procedurally generated maze. The
   game was made in 48 hours for the [30th Ludum dare][between-ld] game jam 
   using [Libgdx][libgdx]. Code is on [Github][between-repo].

[gh-prof]: https://github.com/Alaxe/ "Github profile"
[cf-prof]: http://codeforces.com/profile/perchema/ "Codeforces profile"
[ioi-stats]: http://stats.ioinformatics.org/people/5853 "IOI stats"

[judgesystem-deploy]: https://judgesystem.tk/ "Judge system"
[judgesystem-repo]: https://github.com/Alaxe/judgeSystem/ "Judge system repo"

[stealth-deploy]: http://perchema.tk/stealth/
[stealth-repo]: https://github.com/Alaxe/stealth/
[phaser]: http://phaser.io/
[tiled]: http://www.mapeditor.org/

[chocho-deploy]: http://perchema.tk/ChochoRun/
[chocho-repo]: http://github.com/Alaxe/ChochoRun/
[libgdx]: https://libgdx.badlogicgames.com/

[between-deploy]: http://perchema.tk/BetweenWorlds/
[between-repo]: http://github.com/Alaxe/BetweenWorlds/
[between-ld]: http://ludumdare.com/compo/ludum-dare-30/?action=preview&uid=38747
