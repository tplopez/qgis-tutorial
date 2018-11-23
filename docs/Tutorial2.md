# Tutorial 2: Working with QGIS

## **_Overview and Data_**
In this tutorial, we will interact with the main elements of the QGIS interface. These main elements are those which are basically common to any workflow. Another important feature of QGIS are the plugins, which are processing tools made by other users that are not included in the basic QGIS tools. These plugins are often very useful. We will also learn how to load data into the Map Canvas and use the Digitizing tools to edit the data. Finally, we will learn how to create a thematic map and export it as a .jpeg, .pdf (or other formats).


**_Learning objectives_**
1. Become familiar to the QGIS user interface
2. Become familiar with QGIS Plugins
3. Learn to navigate through the interface (Workflow)
4. Load data into the Map Canvas
5. Learn to manipulate polygon shapefiles
6. Symbolize maps (Thematic maps for qualitative attributes)
7. Create and import map as .jpeg or other image formats

**_Data used in this tutorial_**

* [U.S. State Boundaries](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html)
* [U.S. Climate Regions*](docs/data/conusclimateregion.zip)

*Note*: The U.S. Climate Regions is polygon shapefile created by Tania Lopez based on the official [NOAA Climate Regions](https://www.ncdc.noaa.gov/monitoring-references/maps/us-climate-regions.php)


1. Open QGIS. Same window as the one shown in Fig. 1 will be displayed in your screen.

![Fig. 1 QGIS Interface with each element labeled. Source: QGIS Training Manual](https://docs.qgis.org/2.8/en/_images/gui_numbered.png)
_Fig. 1 - QGIS Interface with each element labeled. Source: [QGIS Training Manual](https://docs.qgis.org/2.8/en/docs/index.html)_

2. Identify each element of the QGIS GUI:

    _a)_ Identify the __Map Canvas (3)__. This is were our data (e.g. maps, road networks, rivers, etc.) will be displayed.

   _b)_ Identify the __Browser Panel (5)__. This panel becomes very handy when loading data into QGIS. The different buttons correspond to different types of data.

    _c)_ Identify the __Layers Panel (1)__. When we load data into QGIS using the buttons in the Browser Panel, it will be stored as a "layer" and displayed in this panel. We will see other features of the Layers Panel later in this Tutorial.

    _d)_ Identify the __Tool Bar (2)__. The different buttons in this bar allows us to open a new project, a recent project as well as save the current project. Starting from the glove-shaped cursor button, the buttons to the right allow us to navigate through the Map Canvas (3).

    _e)_ Identify the __Status Bar (2)__. This bar shows information about the current map.


3. Navigate through the Plugins interface.

    a) Go to the QGIS Menu Bar (In MacOSX, it is located at the very top of the screen) --> Plugins --> Manage and Install Plugins.
    Same window as shown in figure 2 should be displayed.
    ![Fig. 2 QGIS Plugins Interface. Source: QGIS Training Manual](https://docs.qgis.org/2.8/en/_images/get_more_plugins.png)
    _Fig. 2 - QGIS Plugins Interface. Source: [QGIS Training Manual](https://docs.qgis.org/2.8/en/docs/index.html)_

    b) In the Plugins menu, go to the Settings tab, located in the menu to the left. Mark: _Show also experimental plugins_

    c) In the Search bar at the top of the window, search for the following plugins that we will be using later: **Digitizing Tools, Zonal Statistics and Point Sampling**

    d) Go to the Installed tab and verify that all installed plugins in the previous step are checked. (This enables their use in QGIS).

    e) Close the Plugins window. Click the Plugins Menu in the QGIS Menu Bar. Verify that **Digitizing Tools** is now part of the menu. Where are the other two installed plugins located? If you cannot find them under Plugins, go to Help (again in the QGIS Menu Bar) and type the plugin name. Slide the cursor to the entry with the plugin name, and QGIS will show the path to the plugin menu you are looking for. Try with the **Point Sampling** Tool that we downloaded before.

4. Create a Thematic Map and export it. Data that is used in this tutorial is available through the repository, but we will download together the State Boundaries data from TIGER.

    a) Click on this [link](https://www.census.gov/geo/maps-data/data/tiger.html?#) to go to the official U.S. Census TIGER products.

    b) Go to **Cartographic Boundary Shapefiles**

    c) Click on **STATE**

    d) Download the cb_2017_us_state_500k.zip into the directory of your choice[^1]

    e) Unzip the file. Notice that there are many files in the folder. Each file contains different information requried by QGIS to read and load correctly the data. For instance, the .prj file contains information about the [**Map Projection**](https://en.wikipedia.org/wiki/Map_projection).

    f) Go back to QGIS.
    g) In the Side Toolbar, click the first button. Same window as shown in figure 3 will be displayed in your screen.

    ![Fig. 3 - Add Vector Layer menu. Source: [Free and Open Source GIS Ramblings](https://anitagraser.com/)](https://underdark.files.wordpress.com/2011/06/add_wfs_geojson.png)

    _Fig. 3 - Add Vector Layer menu. Source: [Free and Open Source GIS Ramblings](https://anitagraser.com/)_

    h) Select File as Source Type, and navigate to the unzipped folder with the data we downloaded earlier. Select the file whose extension is **_.shp_**. This file is the *Shapefile* that contains the polygon's information (in our case, each state is a polygon). Finally, click Open. The U.S. will be displayed in the Map Canvas, and the data will be added as a layer in the Layers Panel with the same name as the original file.

     i) Click on the cb_2017 layer in the Layers Panel. Clicking on the layer makes it active, meaning that if we do any edits or selections, they will be done to the current active layer.

     j) We will edit the layer and delete some of its polygons for illustrative and data availability purposes. In the Tool Menu, click on the button with a yellow square inside a discontinued line square and a cursor. This buton allows us to select polygons out of a layer by drawing a rectangle over them or just by clicking on each.

     k) In the Map Canvas, carefully draw a rectangle that encloses Alaska. Once you have selected Alaska (it will turn yellow colored),press the shift button. While keeping pressing the shift button, draw rectangles on the U.S. islands to select them. The only polygons that must not be selected are in the Contiguous United States.

     j) In the Tool Bar, click on the pencil button. This button allows editing on the current active layer. The map in the canvas will turn red, which is a sign that it is ready to be edited.

     k) Click on the red trash can button. This button will delete only the selected polygons. If you see any red colored area that is not within the contiguous United States (CONUS), repeat procedure above from k) and delete that area.

     j) Once the only remaining polygons in the map canvas are within the CONUS, click again the pencil button and save the edits.

     k) Zoom-in the U.S. by clicking on either the magnifying glass with the '+' symbol or the magnifying glass with three arrows pointing outwards. The Map should be streched out, covering most of the map canvas area.

     l) Following steps **g) through h)** load the U.S. Climate Regions into the Map Canvas. A second layer will be added into the Layers Panel, named **ClimateRegions**.

     m) Right-click on the **ClimateRegions** layer on the Layers Panel. Click on _Open Attribute Table_. This action will open another window.

     n) Examine the window that was opened. This table contains different information of each of the polygons that are contained in the layer. In this case, the ClimateRegion Attribute table contains two features: _GEOID_ and *Clim_Regio*. Each polygon then has an associated climate region.

     o) Close the Attribute Table. The map as it currently stands is not very informative. Let's construct a thematic map, showing the different climate regions in the U.S. Double-click on the ClimateRegions layer in the Layers Panel. This action will display a new window in which we can control the layer properties.

     p) If the window doesn't automatically opens on the Style tab, click on it from the menu on the left. Select Categorized, and for column *Clim_Regio*.

     q) For Color Ramp, select _New color ramp_. A small window will be displayed. Select ColorBrewer from the menu and click OK. Another window will be displayed. In the Scheme name, select Set3 with 9 colors and click OK. NAme the color ramp (you can leave the default name) and click OK. Click the *Classify* button below the big white rectangle. At the window bottom, click Apply and then OK.

     r) We will next label each region. Double-click on the ClimateRegions layer in the Layers Panel to open its properties. Go to Labels on the left menu. Select _Show labels for this layer_. Label with *Clim_Regio*. In the little left menu, click on Buffer. Mark the _Draw text buffer_. At the window bottom, click Apply and then OK. We have completed our first Thematic Map. This type of maps depict categorical data.

     s) Let's import the map we created as a high resolution, professional .jpg (or other) file so that it can be added to a document. In the QGIS Menu Bar, click on _Project_ --> _New Print Composer_. Assign a name to the composer (you can leave it empty), click OK. Same window as figure 4 will be displayed in your screen.

    ![Figure 4. - QGIS Blank Composer Window. Source: [QGIS User Guide] (https://docs.qgis.org/2.18/en/docs/user_manual/)](https://docs.qgis.org/2.18/en/_images/print_composer_blank.png)
    _Fig. 4 - QGIS Blank Composer Window. Source: [QGIS User Guide](https://docs.qgis.org/2.18/en/docs/user_manual/)_

    t) In the QGIS Menu Bar, go to Layout --> Add Map. Click anywhere on the canvas and by moving the cursor, draw a rectangle that will define the map size. If your canvas is too big, click on the magnifying glass with arrows pointing outwards to fit the canvas size to your screen.

    u) If you are not satisfied on the map size, go back to the QGIS Main Interface, and use the Magnifying Glass tool to draw a rectangle that fits precisely the U.S. Since we zoomed in the map on the main Map Canvas, there will be some changes applied to the composer too. Go back to the Composer window, and click the Refresh Button in the Tool bar. If that doesn't work (sometimes it doesn't), delete the map and add it again following t).

    v) When a composer item is selected, a menu to edit its properties will be displayed to the right. Here you can remove the white background, among other actions. Remove the background for the current map item.

    w) Since we already labeled each polygon, we do not need a legend, but we do need a title. Go to Layout --> Add Label. Click anywhere on the composer canvas to add text. Adjust the size of the label box so that text is displayed correctly and place it on top of the map. In the Item Properties menu on the right, we will edit the text, font and size. Add another label, this time citing the source [NOAA Climate Regions](https://www.ncdc.noaa.gov/monitoring-references/maps/us-climate-regions.php) and place it below the map. Do not forget to put the year of retrieval of this data.

    x) The map is ready to be exported. Go to the QGIS Menu Bar, click on _Composer_ --> Export as image. A new window will be displayed, give a name to the image that will be generated and select a picture format. Once you have done that, another window where to specify the resolution and the size of the map will be shown. Keep the default resolution and check the box _Crop to content_.

----
### Continue to [Tutorial 3](Tutorial3.md)
### Back to [Main Page](https://mushimu.github.io/qgis-tutorial/)


[^1]: All files to download in this page are State boundaries. The only difference is the resolution. For instance, the boundaries in cb_2017_us_state_20m.zip are drawn at high resolution and the file will be quite heavy. We are downloading the lowest resolution map since we will be just symbolizing the map.
