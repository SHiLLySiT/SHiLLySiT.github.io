---
title: "Celeste Playdate Port"
company: default
date: "2022-12-01"
cover: "/projects/celeste-pd/cover.png"
media: [
  "/projects/celeste-pd/gameplay.gif",
  "/projects/celeste-pd/screenshot1.png",
  "/projects/celeste-pd/screenshot2.png",
  "/projects/celeste-pd/screenshot3.png",
]
tags:
- project
- game
layout: project
---

[Celeste Classic](https://maddymakesgamesinc.itch.io/celesteclassic) is a game available on PICO-8 created by Noel Berry and Maddy Thorson. This was a precursor to later, more well known release on major platforms: [Celeste](https://www.celestegame.com/).

However, _this project_ is an unofficial port from [PICO-8](https://www.lexaloffle.com/pico-8.php) to [Playdate](https://play.date/), by Rémi Parmentier (aka [hteumeuleu](https://www.hteumeuleu.com/)).

The port was made to be as faithful as possible to the original game, but here are a few notable changes:
- The game is in black and white only. A lot of visual elements have an outline to make them more readable. But this does not impact their original hitbox.
- The game is rendered at 256×240 from the original 128×128. Four pixel lines are cropped at the top and bottom of the screen. The game can be played at its original resolution by disabling the Fullscreen option available in the game’s menu.
- Assist mode is available under the game’s menu. This allows players to skip a level, change the game speed to 0.5×, get infinite dashes, and enable invincibility. If assist mode is used during a run, a mention is added on each level in the lower right corner, as well as in the pause screen and the final score screen.


## My Role
I offered my help when hteumeuleu announced their work on the port in the Playdate Discord. My contributions were focused on getting the game performing well on the Playdate. Many optimizations were based on things [I learned while optimizing Suborbital Salvage](https://gamesrightmeow.com/garden/02a8564b90d94d25856783ec776650f2/).

## Technologies
Playdate, Lua

## Key Contributions
- Optimized collision checking by changing the hitbox data structures to to contiguous arrays to leverage gains from data locality.
- Added integer ids to entities that could be used to compare entities instead of the tables themselves.
- Put entities into separate type arrays to reduce the amount of collision checks happening per frame.
- Inlined various functions and variables for some small gains.

## Links
- [Download on Itchio](https://hteumeuleu.itch.io/celeste)
- [Pull request on Github](https://github.com/hteumeuleu/celeste/pull/1)

