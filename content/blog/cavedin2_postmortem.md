+++
title = "Caved In 2: Post Mortem"
date = "2013-12-18"
icon = "/images/blog.svg"
categories = ["Post Mortem"]
Description = "Caved In 2 is the sequel to the original game that I created for Ludum Dare #21. Since the original was created in such a sort amount of time, I didn’t get to fully explore the ideas I had for the game..."
+++

### What is Caved In 2?

![cavedin2_dirt](/projects/cavedin2/screen1.png)

Caved In 2 is the sequel to the original game that I created for Ludum Dare #21. Since the original was created in such a sort amount of time, I didn’t get to fully explore the ideas I had for the game. The sequel is meant to fill in the gaps that the original missed, such as, a overhauled lighting systems, monsters, and power ups.

### What Went Right

__Hook, line, and sinker.__ From the start, the core mechanic was fun and addicting – digging around looking for ores and exploring the randomly generated caves. The addition of monsters and an overhauled lighting system really helped with exploration.

__The sky is falling!__ Early in development, I realized I had an issue with continually pushing the player forward. Sure its fun just digging around, but I really wanted them to keep moving forward. Eventually came up with the integrity system. If you haven’t played the game, the integrity (represented by the percentage in the HUD) decreases with every block removed. The lower the integrity, the higher the chance a cave in will occur. The strength of each level gets weaker as you descend, making later levels harder.

![cavedin2_moss](/projects/cavedin2/screen2.png)

__Let’s slap some lipstick on this pig.__ A friend of mine also made a suggestion of different themes the deeper you get. I ended up adding three additional themes, however, it seems the majority of players barely get to the moss theme before rage quitting. Oops. In the latest patch I actually shortened the number of levels you must descend before seeing another theme.

![cavedin2_editor](/projects/cavedin2/ogmo.png)

__To infinity and beyond.__ The original caved in suffered from too much procedural generation – generated caves weren’t interesting and they would be sometimes really weird layouts. I still wanted to have the almost infinite levels, but I also wanted to make sure I had more control over them in the sequel. After many iterations, I eventually came up with a ‘room stitching’ method. What the heck is that you ask? Basically, I designed a pool of “rooms” in Ogmo which were basically just all dirt room with hand-carved caves and a few manually placed props. I also gave rooms tags to determine what sort of content they contained so the game could decide what rooms it wanted to use. Then I used a script I wrote with AutoHotKey to stitch all of the rooms together into a single XML file. When a level is generated, it chooses a room and then randomizes all the dirt tiles with ores and rock, then randomly places items and monsters on open tiles.

### What Went Wrong

__Are we there yet?__ Looking back on when I first started Caved In 2, I realized I had started it almost a year ago! I had intended it to be a quick sequel, but I ended up getting stuck on making the game ‘flow’ right. I also had a lot going on this past year which got in the way and really slowed development. I basically spent the last 3 months working on the last 10%. But you know what they say, the last 10% is 90% of the project.

__Getter done.__ I was a little to eager to finish the game and push it out the door, and as a result there were a few obvious things that I didn’t do. Most notably – alternative controls and a mute button (both of which I’ve added now). There were also some bugs that I should have tested for, such as the bonus points not being included with the score sent to the Mochi score board. Doh!

__What a mess.__ I think this is something all programmers have a problem with for awhile – keeping the code base neat. Caved In 2 was started after my first game with Bullet Proof so I was in the process transitioning to a different way of organizing projects and how I structured my code. As a result, the source was had clashing naming convention and overall was just a mess. The last stretch I did before releasing the game was the worst as I had to got back to some very early code to make changes. Yuck.

Until the next game…