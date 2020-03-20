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

## Game logic

### `10 DEFINT A-Z:SCREEN 2,0,0:COLOR 5,0,0:W=0:FOR N=0 TO 7:READ V:VPOKE BASE(14)+N,V:NEXT N:V=16:X=14`

`DEFINT A-Z` declare all variables as integer, to make sure we run as fast as possible, without decimals calculations.
`SCREEN 2,0,0` initialize the high resolution graphical mode (256 x 192 pixels, 16 colors), adjust sprites to be small sizes with 8 x 8 pixels and disable key clicks.
`COLOR 5,0,0` sets the foreground color to 5 (dark blue), background and border colors to 0 (transparent).
`W=0` initialize our flow state control to indicate a left-to-right level flow (0=left-to-right, 1=right-to-left). This flow is used to check if the flea achieves the end of the level, so we need to know which side it is.
`FOR N=0 TO 7:READ V` we use a FOR loop to read all the 8 values that will compound the sprite image bitmap.
`VPOKE BASE(14)+N,V:NEXT N` this is a small optimization for less code: we poke the sprite bitmap directly into VDP memory, using built in BASIC VPOKE command and retrieving the address of the start of sprites memory using BASE(14). The BASE command get information from VDP registers and the 14 one is the sprite memory base address.
`V=16` is the variable that holds the difficult level. Lower the value, more hard it is. We start with i higher value here.
`X=14` holds the flea X position at the screen, we need to initialize here due to the fact that each level starts from a different side of the screen, so a new game always start from the left side. Also, it have a small displacement to make some space between the platform at the edges of the screeen, so the player have to be really precise when landing at them. My initial idea was to limit the movement at both sides of the screen, but this makes the game play slower and i wanted to achieve a very fast and smooth one!
