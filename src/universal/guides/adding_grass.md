# Tutorial Name
> This guide was written by SpagoAsparago

This is a tutorial on how to add wild grass to existing maps. It requires the use of DSPRE (Gen 4) or CTRMap and either BasicPerHanlder/SAK (Gen 5), in addition to Blender and PDSMS.

--- 
## Table of Contents
* [Extracting the Map Model](#section)
  * [Gen 4](#subsection)
  * [Gen 5](#subsection-2)
* [Converting the Model in Blender](#section-2)
* [Adding the Grass tiles](#section-3)
* [Editing Tile Permissions](#section-4)
* [Assigning an Encounter files](#section-5)
  * [Gen 4](#subsection)
  * [Gen 5](#subsection-2)

## Extracting the Map Model



### Gen 4
Load your game into DSPRE, then go to the Header Editor and search the map you want to add grass tiles to. 

Click `Open Matrix`, you will be redirected to Matrix Editor in the Headers Tab, which will have highlighted the corresponding cell of the map you've selected.

Switch to the `Map Files` tab in the same editor and double click on the spot that was previously highlighted. 
You will be sent to the Map Editor, from where you can export the map model by going to the `3D Model` tab and clicking `Export DAE`. 
Export the Tile Permissions file from the `Move Permissions` tab as well.

### Gen 5
Load your game into CTRMap, then go the `Zone Loader` tab and select the map you want to add grass tiles to.
From the top bar go to `File`>`Serialize Scene` and save the resulting file. 

Now launch Creative Studio (you can do so from the *Tools* button in the top bar) and from *Import*>*Generic* select the file you just exported.
From the dropdown menu on the left, open the `Models` folder and check which one is the map itself.
Then click `Export`>`COLLADA`. From the settings, you want to make sure that the first setting has the `Single Model` option checked, and that the model containing the map is selected. You can leave the rest as deafult. 

## Converting the Model in Blender
You need to use Blender in order to convert the map model to OBJ, so that it can be loaded into PDSMS. Any version of Blender is fine for this.

Launch Blender, then go to `File`>`Import`>`Collada (.dae)` and select your previously exported DAE file. The model will be loaded it and should have an orange outline.
Now type S + 0.0625 + Enter to scale the model to the correct size for PDSMS. Then go to `File`>`Export`>`Wavefront (.obj)`. Make sure to check **Selection only** and leave anything else as default.
Save the resulting OBJ file somewhere and open PDSMS.

## Adding the Grass tiles
In PDSMS, make a new empty map and make sure you're using a tileset containing the grass tiles. Go to `Tools`>`TileSet Editor` then click the `Add Tiles` button and check the `Flip YZ` option.
Select your previously exported OBJ file, then close the TileSet Editor and go back to the map.

Place the new tile you've added in the center of the grid layout (make sure it's centered properly). 
You can add the grass tiles by selecting a different layer above the one containing the tile you've just placed.

## Editing Tile Permissions
While grass tiles has been added to the map, this is purely a visual effect and will not have any change without changing the move permissions and later assigning an encounter file to the map itself.
Open the Collision Editor and click the *Import PER* button, selecting the movement permission file you previously extracted.

<img src="https://images.unsplash.com/photo-1549740425-5e9ed4d8cd34?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxjb2xsZWN0aW9uLXBhZ2V8MXwzOTU0NTB8fGVufDB8fHw%3D&w=1000&q=80" alt="Trulli" style="width:100%">

## Assigning an Encounter file

### Gen 4

### Gen 5
