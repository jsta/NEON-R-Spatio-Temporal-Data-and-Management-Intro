---
layout: post
title: "Spatial Intro 08: Intro to Spatial Metadata -- Spatial Resolution and
Spatial Extent"
date: 2015-10-22
authors: [Leah A. Wasser, Megan A. Jones]
contributors: [ ]
dateCreated: 2015-10-23
lastModified: 2017-12-11
packagesLibraries: [ ]
category: [self-paced-tutorial]
tags: [R, spatial-data-gis]
mainTag: spatial-data-management-series
workshopSeries: [spatial-data-management-series]
description: "This lesson covers the key spatial attributes that are needed to work with
spatial data including: Coordinate Reference Systems (CRS), Extent and spatial resolution."
code1: /R/dc-spatio-temporal-intro/07-spatial-resolution-extent.R
image:
  feature: NEONCarpentryHeader_2.png
  credit: A collaboration between the National Ecological Observatory Network (NEON) and Data Carpentry
  creditlink:
permalink: R/key-spatial-metadata
comments: true
---

{% include _toc.html %}

## About

This lesson covers the key spatial attributes that are needed to work with
spatial data including: Coordinate Reference Systems (CRS), Extent and spatial resolution.

**R Skill Level:** Beginner - you've got the basics of `R` down.

<div id="objectives" markdown="1">

# Goals / Objectives

After completing this activity, you will:

* Understand that there are necessary spatial metadata associated with and/or
embedded in the data
* Understand that there is potentially ancillary data associated with individual
elements in vector data files (like NEON tower data (point), road (line), watershed (polygon)).


## Things You’ll Need To Complete This Lesson
To complete this lesson you will need the most current version of R, and
preferably, RStudio loaded on your computer.

### Install R Packages

* **NAME:** `install.packages("NAME")`

* [More on Packages in R - Adapted from Software Carpentry.]({{site.baseurl}}R/Packages-In-R/)

### Download Data


****

{% include/_greyBox-wd-rscript.html %}

**Spatial-Temporal Data & Data Management Lesson Series:** This lesson is part
of a lesson series introducing
[spatial data and data management in `R` ]({{ site.baseurl }}tutorial/URL).
It is also part of a larger
[spatio-temporal Data Carpentry Workshop ]({{ site.baseurl }}workshops/spatio-temporal-workshop)
that includes working with  
[raster data in `R` ]({{ site.baseurl }}tutorial/spatial-raster-series),
[vector data in `R` ]({{ site.baseurl }}tutorial/spatial-vector-series)
and  
[tabular time series in `R` ]({{ site.baseurl }}tutorial/tabular-time-series).

****

### Additional Resources
* Read more on coordinate systems in the
<a href="http://docs.qgis.org/2.0/en/docs/gentle_gis_introduction/coordinate_reference_systems.html" target="_blank">
QGIS documentation.</a>
* NEON Data Skills Lesson <a href="{{ site.baseurl }}/GIS-Spatial-Data/Working-With-Rasters/" target="_blank">The Relationship Between Raster Resolution, Spatial extent & Number of Pixels - in R</a>

</div>

## Spatial Metadata
There are three core spatial metadata elements that are crucial to understand
in order to effectively work with spatial data:

* **Coordinate Reference System** (CRS),
* **Extent**
* **Resolution**



## Spatial Extent
The spatial extent of a spatial object is just how much area does it cover. A
map of Paris has a smaller spatial extent than a map of all of France.  

### Units
The units of the extent are defined by the coordinate system that the spatial
data is in.  

### Extent in Vector Data
GRAPHIC FROM COLIN

### Extent in Raster Data
The spatial extent of a raster, represents the x,y coordinates of the corners
of the raster in geographic space. This information, in addition to the cell
size or spatial resolution, tells the program how to place or render each pixel
in 2 dimensional space.  Tools like `R`, using supporting packages such as
`rgdal`, and associated raster tools have functions that allow you to view and
define the extent of a new raster.


    # View the extent of the raster
    DEM@extent

    ## Error in eval(expr, envir, enclos): object 'DEM' not found

<figure>
    <a href="{{ site.baseurl }}/images/hyperspectral/pixelDetail.png">
    <img src="{{ site.baseurl }}/images/hyperspectral/pixelDetail.png"></a>
    <figcaption>The spatial resolution of a raster refers the size of each cell
    in meters. This size in turn relates to the area on the ground that the pixel
    represents.</figcaption>
</figure>


<figure>
    <img src="{{ site.baseurl }}/images/spatialData/raster2.png">
    <figcaption>If you double the extent value of a raster - the pixels will be
    stretched over the larger area making it look more "blury".
    </figcaption>
</figure>

### Calculating Raster Extent
To calculate the extent of a raster, we first need the bottom left x,y
coordinate of the raster. In
the case of the UTM coordinate system which is in meters, to calculate
the raster's extent, we can add the number of columns and rows to the x,y corner
coordinate location of the raster, multiplied by the resolution (the pixel size)
of the raster.

Let's explore that next.





