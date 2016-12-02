+++
title = "Caved In 2: Level Generation"
date = "2013-04-23"
categories = ["Devlog"]
Description = "I love procedural content, especially when it comes to randomly generated levels. Not only are such systems fun to set up, but it provides almost endless experiences without having to tediously design a butt-load of levels..."
+++

I love procedural content, especially when it comes to randomly generated levels. Not only are such systems fun to set up, but it provides almost endless experiences without having to tediously design a butt-load of levels (don’t get me wrong though, handcrafted levels made with love and care are also as fun to play). Of course there is a fine line between how much should be randomly generated and how much should be predefined. There’s a certain point where randomness becomes a little too random and detracts from the fun of the game. For example, in the first Caved In I took a rather easy route with level generation:

 1. Fill the level with dirt.
 2. Based on weights for each block type choose one. Then find a random square shaped-area in the level. This varies the tiles in the level creating deposits of coal, gold, water, and etc. Do this a few times.
 3. For each tile in the square area, change the dirt tile to the chosen block based on a specified chance (if I remember correctly, blocks had a 30% chance to dirt). This ensures we don’t have square areas of tiles.
 4. Find a random square-shaped area and change all the tiles to floor tiles, which creates (boring) caves. Do this a few times.
 
Resulting levels were “unique” each time but not very interesting because they lacked defining features or fun caves to explore. In Caved In 2 I’ve decided to take a different route. Instead of randomly generating the level, I broke it into four 12×12 tile “rooms”. The rooms are designed by hand in Ogmo by laying out dirt tiles to define caves and placing object spawns (such as loot, power ups, and etc).

![cavedin2_editor_room](/projects/cavedin2/editor_room.png)

_A bare room designed in Ogmo._

The rooms are then compiled into a XML “room database” using a script I wrote in AutoHotKey. When the level is generated, it randomly chooses rooms and stitches them together to form the entire level. The dirt tiles in the rooms are then replaced with other tiles using a similar algorithm found in the original Caved In, although it’s been refined to provide a better spread of block types.

![cavedin2_game_room](/projects/cavedin2/game_room.png)

_Same room from above in-game…although some gravel caved in above where I dug in._

In the end, levels are still randomly generated but provides me with a bit more control to help give the levels a more personal touch. In the coming weeks I’m going to be churning out loads of more rooms as I get closer to release along with more props and decorations. Stay tuned!