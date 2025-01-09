# stormworks-additional-workbenches-mod
benchwork in the workstorm


This page is to keep track of my XML edits so I don't cry later.
But will probably just be abandoned cause I hate editing XMLs to do anything, but I'll keep my findings here I guess.

Local Mod Folder: (User)\AppData\Roaming\Stormworks\data\mods\
Mod folder has to be created if you don't have one.


# Decoding transformation
Example:
<transform 00="-0" 02="-1" 20="1" 22="-0" 30="-1488" 31="8.8" 32="50.973915"/>

Transform is split into 2 separate parts, Rotation and Coordinates

## Rotation
Transform rotation is represented as Quaternions as XYZW on a scale of -1 to 1 usually. The unity engine uses to magically calculate rotational values, I don't have a math degree and thus can't explain how these function. You cna probably use a visualizer to understand it a bit better or get a degree in math, whichever.

According to an older post, these are rotational values to get 90 degree turns, leaving the rotational values blank will result in the object facing it's default direction. Objects of course have different default directions they face. Inherently, the Workbench always faces West, thus a 90 Degree Right would make it North but for some reason the Edit Zone faces South by default.

90 right:
00="-0" 02="-1" 20="1" 22="-0"

180:
00="-1" 02="0" 20="-0" 22="-1"

270 right (90 left):
00="-0" 02="1" 20="-1" 22="-0"

As noted: I have no clue which of these values are which, I'm assuming they are in either this order X, Y, Z, W or W, X, Y, Z.

- 00="#"
- 02="#"
- 20="#"
- 22="#"

## Coordinates
Transform coordinates are relative to the tile's origin center, I think. To find these coordinates, load the tile in the mission locations part of the addon editor. Then place an object and look at the coordinates, those coordinates should be the correct ones for your object placement.

- 30="#" (X)
- 31="#" (Y)
- 32="#" (Z)
