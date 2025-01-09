# stormworks-additional-workbenches-mod
benchwork in the workstorm


This page is to keep track of my XML edits so I don't cry later.
Local Mod Folder: (User)\AppData\Roaming\Stormworks\data\mods\
Mod folder has to be created if you don't have one.


# Decoding transformation
Example:
<transform 00="-0" 02="-1" 20="1" 22="-0" 30="-1488" 31="8.8" 32="50.973915"/>

Transform is split into 2 separate parts, Rotation and Coordinates

## Rotation
Transform Rotation is represented as Quaternions on a scale of -1 to 1. The unity engine uses these to store magical rotational values.

According to an older post, these are rotational values to get 90 degree turns, remember that many objects have different default rotational values.
[
90* right:
00="-0" 02="-1" 20="1" 22="-0"

180*:
00="-1" 02="0" 20="-0" 22="-1"

270* right(90* left):
00="-0" 02="1" 20="-1" 22="-0"
]

00="#" 
02="#"
20="#"
22="#"

## Coordinates
Transform coordinates are relative to the tile's origin center, I think. To find these coordinates, load the tile in the mission locations part of the addon editor. Then place an object and look at the coordinates, those coordinates should be the correct ones for your object placement.

30="#" (X)
31="#" (Y)
32="#" (Z)
