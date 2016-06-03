**Use Download button (on the right side of this page) to download.**  
**If you use right click on each file to save, you'll get an HTML file.**


This is a more practical (just for me) modification of well known voronoi script by
[@fabiantheblind](https://github.com/fabiantheblind/Illustrator-Javascript-Voronoi)
using the voronoi library by
[@gorhill](https://github.com/gorhill/Javascript-Voronoi).  
Please see the original repositories for more fantastic use cases and usage of the library.  

**test environment**:  
Adobe Illustrator CC 2015 (Mac) ... ok  
Adobe Illustrator CS3 (Win) ... It needs to modify "include" directive. See inside "lib" folder for details.

voronoi_from_selected_objects.jsx
======================
This script draws a Voronoi diagram based on the central coordinate of each object in current selection.  
The object which has the largest size (width or height) in the selection is used for the bounds for drawing.
(Therefore, **make sure** to include the object becoming the bounds (=frame) in the selection.  This object is excluded from the targets for the Voronoi calculation.)  The objects located outside of this bounds are ignored.  
The lines drawn are put into a group.  And the filled paths are put into another group.

**Note**: This script requires '**rhill-voronoi-core.js**' (by
[@gorhill](https://github.com/gorhill/Javascript-Voronoi)
) included in this repo.
You need to place it under the "lib" folder under "Scripts" folder of Adobe Illustrator.

Again, it uses the central coordinate of each "object". It can be various type in Illustrator, like the following image.

![desc_voronoi_various_objects](https://github.com/shspage/Illustrator-Javascript-Voronoi/raw/master/img/desc_voronoi_various_objects.png)

Note that the grouped object is recognized as one object.  
In this case, "object" means an object which is selected with a click using Select Tool (black arrow).  
You can release groups before you run the script.  But if the script force releasing groups,
you can do nothing, even if you don't want to release them.
So this script doesn't extract objects from groups at all.
Please be careful about the construction of groups in the selection.
If there are less than 3 "objects" in the selection, this script do nothing.


The filled paths are painted in white.  The following image is an example which used 
[noiseFill.jsx](https://github.com/shspage/illustrator-scripts/blob/master/noiseFill.jsx)
 to modify the color after making the Voronoi diagram.

![desc_voronoi_example](https://github.com/shspage/Illustrator-Javascript-Voronoi/raw/master/img/desc_voronoi_example.png)


## changes from the original
* uses the central coordinate of each object in the selection
* draws on the current artboard
* uses the largest object in the selection as an outer frame
* groups and compoundpaths are not released
* text objects are not outlined
* removed coloring options inside the script
* added UI which has a checkbox
* updated the library to the current version, and moved it under "lib" folder

----------------------
## License
Copyright(c) 2016 Hiroyuki Sato  
[https://github.com/shspage](https://github.com/shspage)  
This script is distributed under the MIT License.  
See the LICENSE file for details.  

This script is a modification of following script.

**voronoi_from_selection.jsx**  
[https://github.com/fabiantheblind/Illustrator-Javascript-Voronoi](https://github.com/fabiantheblind/Illustrator-Javascript-Voronoi)  
Copyright (c)  2012 Fabian "fabiantheblind" Moron Zirfas  
Licensed under The MIT License

This software uses the following library that may have a license differing from that of the software itself.
You can find the library and its respective license below.

**rhill-voronoi-core.js**  
[https://github.com/gorhill/Javascript-Voronoi](https://github.com/gorhill/Javascript-Voronoi)  
Licensed under The MIT License  
Copyright (c) 2010-2013 Raymond Hill
  