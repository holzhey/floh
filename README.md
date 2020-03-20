# FLOH

![Floh in game screenshot](https://github.com/holzhey/floh/raw/master/floh.png)


This is a game for the BASIC 10 Liner Contest 2020 based on MSX 1 platform. More about the contest can be found here: https://gkanold.wixsite.com/homeputerium/kopie-von-2020

## Game info

- Title: Floh (flea)
- Platform: MSX
- Author: Alexandre Lehmann Holzhey
- Language: MSX-BASIC 1.0
- Category: PUR-120

## Files description

* README.md: This file, with general information about the game.
* FLOH.BAS: Source code of the game, in BASIC langauge.
* floh.png: Screenshot of the game.
* floh.dsk: Disk image with the game saved inside, for using with emulators.

## The game

You are a flea (floh, in Deutsch) and need to keep yourself alive. Unfortunately, there is a water flooding ongoing and to stay safe it is necessary to keep jumping above the water level. If you stay much time jumping without moving, you start to get tired and will also die. There is a food for the flea at the end of each level, in order to keep going!

## How to play

The flea keeps jumping all the time, you have just to move it to the right or to the left, using th arrows keyboard keys (left or right). The moving is inertial, you control how much factor is added to the movement. You can also reduce the movement, going to the oposite direction.

But be aware that the flea will jump less high at each time. If you stay too much time at the same level, you got killed. Each level is a full moving from the left to the right or from the right to the left. A new level will be rendered and the flea will be kept without movement, to make things easier.

There is no end, but each level will have smaller plataforms to jump. If you get killed, the game restarts from first level.

## Using an emulator

The game was developed on a Sharp Hotbit HB-8000 MSX 1 computer (manufactured at Brazil in 1985). You can use an emulator, i recommend the WebMSX one: https://webmsx.org/?MACHINE=MSX1&DISK=https://github.com/holzhey/floh/raw/master/floh.dsk
Just use the provided URL and when ready type `load "a:floh.bas"`. Could be necessary to enter a date in order to boot the system, in this case just press the ENTER key.
