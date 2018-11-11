# qgis-tutorial
Reference guide for EWRI GIS Tutorial Session.

QGIS version 2.18.20

## EWRI QGIS Tutorial Session
Organized and conducted by Tania Lopez

November 30th, 2018

As environmental engineers, we often need to work with data that has an associated spatial dimension. For instance, working with samples across a river, working with weather station networks, among other examples. Geographical Information System softwares provide numerous advantages when working with such data. ESRI ArcGIS and the open source QGIS are very common tools that have many implemented functions that work specifically for spatial data. 

In this tutorial session, we will introduce the use of QGIS and work through three different tutorials targeted to no-experience and beginner users. The purpose is to give the attendees a general idea about the capabilities of this software.
This tutorial is not intended to cover all capabilities of QGIS (for that there is a course offered in the department that uses ESRI ArcGIS!) but instead give a chance to graduate students who are interested/curious in/about this software, and by attending this tutorial and grasping the basics, might find it useful for their research/coursework/future careers to deepen their knowledge by attending the courses offered at CMU.

This guide is only an overview of the tutorial. Each _Tutorial_ section is organized by the different learning objectives that the tutorial aims to cover followed followed by the data to be used in the tutorial with its respective download links. If there is no download link for a particular dataset, it can be downloaded through this repository. 

Remember, this is not a QGIS user manual. For more information on QGIS, please visit [the official QGIS manual](https://docs.qgis.org/2.8/en/docs/training_manual/index.html)

## Tutorial 1
Overview:
In this tutorial we will briefly talk about the main differences between ESRI ArcGIS and QGIS. Although it is expected that those who attend the tutorial already completed the QGIS installation process, we will also briefly cover the installation for Mac OSX. In geographical information systems software, there are different types of data to deal with. There are two main types, vector and raster data. We will go through the basics in this section since we will be explaining more in the next tutorials. Finally, I will point to different sources of free GIS data that I have used in the past.

**_Learning objectives_**
1. Overview of ESRI ArcGIS and QGIS
2. Get QGIS ready in your laptop (Mac OSX)
3. Differentiate between the types of data that can be used in QGIS
4. Overview of useful sites where to free GIS data

**_Data used in this tutorial_**
_No data_

## Tutorial 2
In this tutorial, we will interact with the main elements of the QGIS interface. These main elements are those which are basically common to any workflow. Another important feature of QGIS are the plugins, which are processing tools made by other users which are not included in the basic QGIS tools. These plugins are often very useful. We will also learn how to load data into the Map Canvas and differentiate between common map projections (This by itself is a large topic, which will not be covered in the tutorial), and discuss why it is important to keep all your data in the same projection. Finally, we will learn how to create a thematic map and export it as a .jpeg, .pdf (or other formats).

**_Learning objectives_**
1. Become familiar to the QGIS user interface
2. Become familiar with QGIS Plugins
3. Learn to navigate through the interface (Workflow)
4. Load data into the Map Canvas
5. Symbolize maps (Thematic/Chropleth maps for qualitative and quantitative attributes)
6. Create and import map as .jpeg or .pdf

**_Data used in this tutorial_**

* [U.S. State Boundaries](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html)
* [U.S. Climate Regions*](../conusclimateregion.zip)
* [U.S. Urban Areas](https://www.census.gov/cgi-bin/geo/shapefiles/index.php)

*Note*: The U.S. Climate Regions is polygon shapefile created by Tania Lopez based on the official [NOAA Climate Regions](https://www.ncdc.noaa.gov/monitoring-references/maps/us-climate-regions.php) 

## Tutorial 3
In this tutorial, we will learn how to filter out data that we are interested in by accessing the data layer's Attribute table. We will then learn how to edit a layer via the Digitilizing Tools Plugin. We will repeat the step 5 from the previous tutorial, however, instead of directly using the "U.S. Climate Regions" layer, we will join a standalone table with each state's climate region and join this table to the state polygon layer. We will learn how to load raster data (.tif files) into QGIS, discuss other raster data formats. We will then learn how to clip a raster layer using the boundaries of another layer and visualize different symbology for rasters. Using the Zonal Statistics plugin, we will compute the average 2017 daily maximum over each state. Finally, we will extract the 2017 daily maximum for each city with population greater than 10,000 by first filtering and then using the Point Sampling tool.  

**_Learning objectives_**
1. Learn to filter data via the Attribute Table
2. Learn to manipulate polygon shapefiles
3. Join standalone tables to polygon data
4. Load different other types of data in the Map Canvas
5. Clip a raster layer and 
5. Compute statistics within specific boundaries using the Zonal Statistics plugin 
6. Sample from raster using a point layer and the Point sampling tool

**_Data used in this tutorial_**
* [U.S. State Boundaries](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html)
* [CONUS 2017 Maximum Daily Precipitation](../2017_dailyannualmaxima.tif)
* [U.S. Urban Areas](https://www.census.gov/cgi-bin/geo/shapefiles/index.php)
* [U.S. Cities and Towns](https://www.sciencebase.gov/catalog/item/581d051ae4b08da350d523ac)

*Note*: The 2017 Annual Maximum Daily Precipitation is a raster file created by Tania Lopez by first extracting the daily maximum at each gridcell center from the .25-degree latitude x 0.25 -degree longitude CPC Unified Gauge-Based Analysis of Daily Precipitation over CONUS gridded data. Raster was created by running an inverse distance weighting to create a continuous field. The original (in netCDF format) CPC Unified Gauge-Based Analysis of Daily Precipitation over CONUS gridded data can be found at this [link](https://www.esrl.noaa.gov/psd/data/gridded/data.unified.daily.conus.html).

## Provide Feedback

The tutorial session is the very first session offered by the Environmental and Water Resources Graduate Student Chapter at CMU, and we hope to expand into other topics depending on the interest of the attendees. How can this tutorial be improved? Did you want other topics to be covered? Please provide your comments [here](Link to survey)

