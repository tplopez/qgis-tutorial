# Tutorial 3: Raster data and more advanced functions in QGIS

In this tutorial, we will learn how to load raster data (.tif files) into QGIS. We will then visualize different symbology for rasters. Using the Zonal Statistics plugin,we will compute the average 2017 daily maximum over each state. Using this data, we will create a Choropleth map. We will learn how to create a point layer based on lat,lon pairs stored in a csv file and sort common trouble that we can come across. Finally, we will learn how to perform queries via the Attribute table of a layer, and create a zoomed map with other professional elements that are required when displaying areas at large scale.

**_Learning objectives_**

1. Load different other types of data in the Map Canvas
2. Compute statistics within specific boundaries using the Zonal Statistics plugin
3. Sample from raster using a point layer and the Point sampling tool
4. Learn to filter data via the Attribute Table
5. Sample from raster using a point layer and the Point sampling tool


**_Data used in this tutorial_**
* [U.S. State Boundaries](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html)
* [CONUS 2017 Maximum Daily Precipitation](data/2017_dailyannualmaxima.tif)
* [Pittsburgh Coordinates](data/PittsburghCoords.csv)

*Note*: The 2017 Annual Maximum Daily Precipitation is a raster file created by Tania Lopez by first extracting the daily maximum at each gridcell center from the .25-degree latitude x 0.25 -degree longitude CPC Unified Gauge-Based Analysis of Daily Precipitation over CONUS gridded data. Raster was created by running an inverse distance weighting to create a continuous field. The original (in netCDF format) CPC Unified Gauge-Based Analysis of Daily Precipitation over CONUS gridded data can be found at this [link](https://www.esrl.noaa.gov/psd/data/gridded/data.unified.daily.conus.html).

## **_Step-by-Step_**

1. Load Raster data into the Map Canvas.

    a) Download (if you have not yet) the required data for this tutorial.

    b) On the same project, click on `Add Raster Layer` button in the Side Tool Menu (second from the top). This button is only for loading raster (.tif) data into the map canvas. Select the 2017_dailyannualmaxima.tif file. Uncheck the **ClimateRegions** layer in the Layers Panel. You will notice that now we are not able to see the state boundaries in the Map Canvas, because they have been covered by the new raster file that we added. In the Layers Panel, click and move the **cb_2017** layer on top of the **2017_dailyannualmaxima**. We now can't see the **2017_dailyannualmaxima** because the state polygons are filled with color. Let's change this style.

    c) Double-click on the **cb_2017** layer. In the _Style_ tab, click _Simple fill_ on the first white box. Select _Outline: Simple line_ as _Symbol layer type_ and click Apply and OK buttons at the bottom of the window.

    d) Now open the Layer Properties Menu for **2017_dailyannualmaxima** and change the render type to _Singleband pseudocolor_. Choose _Discrete interpolation_, and click the _Classify_ button below the mode. Click Apply and OK buttons at the bottom of the window.

2. Compute statistics within specific boundaries using the `Zonal Statistics` plugin

    a) Locate the `Zonal Statistics` plugin menu. _Hint:_ Recall that Help in the QGIS Menu bar can show you the path if you cannot readily find the tool. A window similar as figure 1 will be displayed. This tool will compute statistics within the zones that we specify. We will compute the average 2017 daily maximum precipitation for each state.


    ![Fig 1. - Zonal Statistics Window. Source: [QGIS User Guide] (https://docs.qgis.org/2.18/en/docs/user_manual/)](https://www.qgis.org/tr/_images/d86b8eb8a72d26a0fcb0bf043c9189e14a4ae125.png)
    _Fig 1. - Zonal Statistics Window. Source: [QGIS User Guide](https://docs.qgis.org/2.18/en/docs/user_manual/)_

    b) By default, the **2017_dailyannualmaxima** will be selected because there are no more raster layers loaded in the working space. Select the **cb_2017** layer for the Polygon layer containing the zones. Choose a name for the output column prefix, and select Mean, Median and Standard Deviation as Statistics. Click OK. (This might take some time depending on your computer specs, and for future reference,the more zones you have, the longer it will take.)

    c) Open the **cb_2017** layer _Attribute Table_. You will see that three new columns have been added as features, starting with the prefix that you selected. Let's create a Choropleth for the mean 2017 daily maximum precipitation.

    d) Open the **cb_2017** Layer Properties Menu. Go to the _Style_ tab and, while being on the Single Symbol style, choose _Simple fill_ for Symbol Layer type. Now, instead of Single Symbol, select _Graduated_. This style is suitable for quantitative data. Select the _yourprefix_mean_ column for Column. Note that _Equal Interval_ is now selected. Click _Classify_ below the big white box, and then on that same box click on the _Histogram_ tab. Verify that data is well distributed on each block. In this case, the data seems to extend until 130 mm, we should try other bin classification. Click on the _Classes_ tab to go back to the bins. This time select _Quantile_ and click _Classify_. Verify again the Histogram. Click Apply and OK buttons at the bottom of the window.

    e) Label the **cb_2017** with each state name as in Tutorial 2.

3. Make a polygon layer using latitude and longitude coordinates.

    a) Click on `Add Delimited Text Layer` button in the Side Tool Menu (third from the bottom). Navigate to the directory where the **PittsburghCoords** file is. QGIS will automatically fill the required fields for adding the layer. If you see something wrong, change it. In this case, everything is correct.

    b) Bring the **PittsburghCoords** layer to the top in the Layers Panel. We don't see it yet on the Map Canvas. Right-click on it and select `Zoom to Layer` to see it on the Map Canvas. What happened? Where was it placed? Listen to the explanation during the tutorial session.

    c) Remove the **PittsburghCoords**. Go to the .csv file and add a "-" sign before the longitude coordinate.

    d) Load **PittsburghCoords** again following step a).

    e) Now the poing will be placed where Pittsburgh is. Open the Layer Properties and change its style.

    f) Locate the `Point Sampling Tool` menu in the QGIS Menu Bar. By default, the **PittsburghCoords** layer will be selected in the _Layer containing sampling points_ because we only have one loaded into our working space. On the _Layers with fields/bands to get values from_ select the **2017_dailyannualmaxima**. Browse to the directory where you have been saving the files used on this tutorial and give a name to the new point layer that will be created, which will have the value of the **2017_dailyannualmaxima** layer at that point added as a feature to the **PittsburghCoords** attribute table. Click OK and close the window.

    g) Verify that the **2017_dailyannualmaxima** is on the new added layer to the canvas.

    h) Label the point with the **2017_dailyannualmaxima** value.


4. Zoom into a selected polygon via the Attribute Table.

    a) Enable the **ClimateRegions** layer and click on it, so that it becomes the active layer. On the Tool Bar, click on `Select features using an expression` button (the yellow square with an E symbol button). Same window as in figure 2 will be displayed.

    ![Fig 2. - Zonal Statistics Window. Source: [QGIS User Guide] (https://docs.qgis.org/2.18/en/docs/user_manual/)](https://docs.qgis.org/2.18/en/_images/function_list.png)
    _Fig 2. - Zonal Statistics Window. Source: [QGIS User Guide](https://docs.qgis.org/2.18/en/docs/user_manual/)_

    b) Click on the arrow on the left of _Fields and Values_ on the menu located in the middle of the window. Other fields will be displayed below, then click on _ClimRegio_. Click on the _All unique_ button at the bottom right corner of the window. All unique names of the **ClimateRegions** layer will appear in the upper box. Double-click on _Northeast_. This action will add 'Northeast' on the leftmost white box. Before 'Northeast' write the following: "Clim_Regio" is 'Northeast'. This expression will select the polygon that meets the condition. Click on the _Select_ button at the bottom right corner. Close the window and go back to the main QGIS interface. Apparently, nothing happened but if you check the Status bar, on the bottom left corner, you will see that it says `"1 feature(s) selected on layer Clim_Regio"`. Uncheck the **cb_2017** and the **2017_dailyannualmaxima** so that the only visible layer is the **ClimateRegions**. You will note that the Northeast polygon is yellow colored, meaning that is currently selected.

    c) Using the `Zoom to selection` button (magnifying class with the yellow square button) in the Tool bar, zoom in the selected polygon, in this case the Northeast polygon from the **ClimateRegions**.

    d) Make visible the **cb_2017** and the **2017_dailyannualmaxima** again.

5. Make a map with legend and other professional map properties.

    a) Open a new print composer from the Menu Bar --> Project and add the current map to the composer canvas. Click on Layout --> Add Legend, and click anywhere on the canvas. A legend will be added. Follow instructions during the tutorial to make fix the map legend. Once finished, export the map and save it as .png file.

---

### Back to [Main Page](https://mushimu.github.io/qgis-tutorial/)

---

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
