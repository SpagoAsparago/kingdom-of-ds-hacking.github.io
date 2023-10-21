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
* [Compressed files]

## Using a Hex Editor

Binary Hacking is done by editing the compiled binaries of the game files. 
For most of the regular stuff like wild encounters and trainers there are tools in place to simplify the process, but sometimes it is still necessary to hex edit things manually.

If you haven't already you need to download a Hex Editor. There are plenty of different softwares that can do it, in this guide I will be using HxD.

For starters you want to load the file you need to hex edit in the program.

## Offsets

An offset is the address of a binary file.

In HxD you can "jump" to certain offsets using the *Search>Go To...* function, or using the shortcut `Ctrl+G`. It will open up a window where you need to enter the offset. Note that offsets are usually indicated with a `0x`, such as `0xAB12DC`, so in this case you only need to enter `AB12DC`.


## Searching the bytes

When you need to instead search for a sequence of bytes (that you already know), you can use HxD Search function or the shortcut `Ctrl+F`, selecting Hex Values and then pasting the bytes you are looking for. 


### Converting from Decimal to Hexadecimal - Little Endian

When it comes to binary all the data is stored in [little-endian format](https://thebittheories.com/little-endian-vs-big-endian-b4046c63e1f2):

To keep it simple, just remember that the order of bytes is always inverted. For example, if you want to search 1212, first convert it to hexadecimal (Windows Calculator programmer mode can come in handy): it will be `04 BC`, swapping the order of bytes we get the little endian number which is `BC 04` in this case.

## Pasting Bytes

Once you are at the right offset you can simply type the bytes you want to replace and save the file.

**Remember to only replace bytes and never expand the size of the original file, unless you really know what you are doing**.
The game expects an exact amount of data, expanding the size of the file will break your game unless you are also accounting for that trough code editing.
If you need to replace a large sequence of bytes, you can paste-replace them with the `Ctrl+B` shortcut.

## Compressed files
All games including HGSS and onwards have their overlay and arm9 files compressed. This is always going to be mentioned in all the guides you can read here but it's worth to keep it in mind. You can use CrystalTile2 to decompress them, and the arm9 in DSPRE project folder is already uncompressed
