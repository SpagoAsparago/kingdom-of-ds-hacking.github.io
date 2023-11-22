# Tutorial Name
> This guide was written by SpagoAsparago.

This is a tutorial on how to export and import buildings in gen 5 games.
You will need to have installed (CTRMap-CE)[https://github.com/kingdom-of-ds-hacking/CTRMapV/releases] as well as the (CTRMapV)[https://github.com/kingdom-of-ds-hacking/CTRMapV/releases] plugin, then create a project of your the game you want to import/export buildings to/from if you haven't already.

--- 
## Table of Contents
* [Exporting Buildings](#section)
  * [Exporting Animations](#subsection)
* [Importing Buildings](#section-2)
  * [Importing Animations](#subsection-2)
The first thing you want to do is load the map you want to export/import your building(s) using the Zone Loader, then open the building editor by clicking the Pokémon Center icon in the World Editor's top bar, and then click *Edit Resource Bundle*

![](ctrmapbuildingeditor.PNG)

## Exporting Buildings
Select the building you want to export from the list on the left side of the editor, then click the *Open in CS* button right below. This will launch Creative Map studio, from where you can export the model in a number of different formats, using the *Export* options from the top bar.

About the different file types you can get, it's worth mentioning:
* COLLADA: exports as **DAE** format
* NNS Resource: exports as **NSBMD**, Nintendo's proprietary format
* WaveFront OBJ: exports as **OBJ** format. The textures will be exported as a separate **mtl** file, keep both in the same directory.

If you're planning to import the building in a gen 4 game, both DSPRE and PDSMS building editors only acccept NSBMD files. For gen 5 games, both OBJ and DAE work but the latter is recommended.

### Exporting Animations
If the building you want to export has an animation, you can export it by selecting the animation on the menu on the right side of the editor after having selected the building, then click the *Open in CS* button right below it.

![](animeditor.PNG)

In Creative Studio, select the animation in the dropdown menu (it will be either in the Material or Skeletal Animation folder), then right click on it > Export and it will be saved as a NSBTA/NSBCA file depending on the animation type.

## Importing Buildings

