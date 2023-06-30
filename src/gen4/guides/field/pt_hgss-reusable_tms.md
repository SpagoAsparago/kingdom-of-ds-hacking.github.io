# How to make TMs Reusable<sup>*(Platinum/HGSS)*</sup>

>This guide was originally written by Drayano and formatted for this wiki by SpagoAsparago.

> The Research was made by Mikelan98 with help from NextWorld and Bagboy.
Mikelan98 has requested that you give credit to him if you implement this in your hack.

This is a guide on how to implement reusable TMs in Platinum and HGSS. The US versions of those games are used, so offsets might be not be the same if you're using a different version.

The tools required are an hex editor and Tinke 0.9.2, or instead CrystalTile2 if you're using HGSS.

--- 
## Table of Contents
* [Extracting the files](#section)
  * [Platinum](#subsection-1)
  * [HGSS](#subsection-2)
* [Hex Editing](#section-2)
  * [Making TMs infinte](#subsection-1)
  * [Removing the TM item count](#subsection-2)
* [Reinserting the files](#section-3)

## Extracting the files
First you need to extract the relative files in order to perform the hex editing
### Platinum
For Platinum the files you need are *arm9.bin* and *overaly9_84*.

Open your ROM in Tinke, search the file, select it and click the extract button.


### HGSS
For HGSS you need to extract *arm9.bin* and *overlay_0015.bin*, but they are compressed unlike in Platinum hence the need for CystalTile2.


## Hex Editing

### Making TMs infinite


### Removing the TM item count



Infinite TMs in Gen IV
---
Let me first preface this by saying that this was figured out by Mikelan98 (with some help from Nextworld and BagBoy to find some of the offsets in different languages). Mikelan98 has requested that you give credit to him if you implement this in your hack.

This is simply a documentation so the information doesn't get lost - I didn't figure out any of this myself!

This is for the American (U) versions of Platinum and Heart Gold / Soul Silver.

Step 1: Extract the relevant files
---
First we need to get the right files out of the ROM.

For Platinum, you'll need the arm9.bin and the overlay_0084.bin files.
For HG / SS, you'll need the decompressed arm9.bin and a decompressed overlay_0015.bin files. (Use the Extract(U) option in crystaltile2 to decompress.) 

Step 2: Edit the code to make the TM quantity not drop after use
---
For Platinum, we want to make the following changes:
* Search for "FE 00 28 07 D1 08 48" in the arm9.bin file.
* Replace the "D1" with "E0" so that it now reads "FE 00 28 07 E0 08 48".

For HG/SS, we want to make the following changes:
* Search for "FD 00 28 07 D1 0A 48" in the decompressed arm9.bin file.
* Replace the "D1" with "E0" so that it now reads "FD 00 28 07 E0 0A 48".

Step 3: Edit the code to make the item quantity not appear for TMs in the bag
---
For Platinum, we want to make the following changes:
* Search for "FF F7 83 FF 04 B0" in the overlay_0084.bin file.
* Replace the first four bytes with "00 00 00 00", so it should now read "00 00 00 00 04 B0".

For HG/SS, we want to make the following changes:
* Search for "81 42 53 D3" in the decompressed overlay_0015.bin file.
* Replace the "D3" with E0 so that it now reads "81 42 53 E0".

Step 4: Rebuild the ROM
---
You'll need to reinsert the relevant files as needed. For HG/SS, you'll need to recompress them when adding them to the ROM by using the "Compression" option to import them back when using crystaltile2.

After that, save and/or build your ROM, and you should find that TMs don't show a quantity anymore, and they also won't disappear after being used.
