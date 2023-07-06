# Hex Editing
> This guide was written by SpagoAsparago

This is a tutorial on how to hex edit your files for the first time.
--- 
## Table of Contents
* [Using a Hex Editor](#section)
  * [Little Endian](#subsection)
* [Offsets](#section-2)
* [Searching the bytes](#section-3)
* [Pasting bytes]
* []

## Using a Hex Editor

Binary Hacking is done by editing the compiled binaries of the game files. 
For most of the regular stuff like wild encounters and trainers there are tools in place to simplify the process, but sometimes it is still necessary to hex edit things manually.

If you haven't already you need to download a Hex Editor. There are plenty of different softwares that can do it, in this guide I will be using HxD.

For starters you want to load the file you need to hex edit in the program.

### Little Endian



## Offsets

An offset is the address of a binary file.

In HxD you can "jump" to certain offsets using the *Search>Go To...* function, or using the shortcut `Ctrl+G`. It will open up a window where you need to enter the offset. Note that offsets are usually indicated with a `0x`, such as `0xAB12DC`, so in this case you only need to enter `AB12DC.

Once you're at the right offset you can simply type the bytes you want to replace and save the file.

## Searching the bytes

When you need to instead search for a sequence of bytes (that you already know), you can use HxD Search function or the shortcut `Ctrl+F`, selecting Hex Values and then pasting the bytes you are looking for. 


### Little Endian

All the data
