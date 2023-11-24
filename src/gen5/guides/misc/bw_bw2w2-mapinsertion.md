# How to insert custom maps and their textures in Gen V games
> This guide was written by Gonhex and was formatted for this wiki by SpagoAsparago


This is a tutorial on how to insert your own maps in generation 5 games, as well as change the Area Data textures.
It is assumed you have already made your map in PDSMS (or Blender) and have all the files already converted. If you're unsure how to do so, check Jay's video on creating a map with PDSMS.
--- 
## Table of Contents
* [Locating the Matrix](#section)
* [Finding the Map file](#section-2)
* [Adding a new Header](#section-3)
* [Inserting the Map](#section-4)
  * [Using BasicPerHandler](#subsection)
  * [Using SAK](#subsection-2)
* [Updating the Area Data](#section-5)

## Locating the Matrix
First you want to find out which matrix you want to insert your new maps into, and check if there is available space or you need a new matrix. If it's Matrix 0, you don't need to do anyting else. If you want to insert your map next to an adiacent existing map but it's not on Matrix 0, open the latter map header on CTRMap Header Editor, and check what Matrix is listed there.

## Finding the map file
Now you have to find the file number of the map you want to replace, you can do so in two ways:

* Using SDSME:
**SDSME is very old and not recommended, if you have to use it only use it for viewing the map header section and don't make any edits with it

* Using GFMatrixEditor:
First you have to extract the matrix narc at a/0/0/9 from the game using Tinke. Then launch GFMatrixEditor and click the GFMat->Pack button



## Adding a new Header

## Inserting the Map

### Using BasicPerHandler

### Using SAK

## Updating the Area Data
