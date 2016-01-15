---
layout: post
title: "Lesson 03: Data About Data -- Intro to Metadata File Formats and Structure"
date:   2015-10-27
authors: [Dave Roberts, Tracy Teal, Kaitlin Stack Whitney, Leah Wasser, Megan A. Jones]
contributors: [ ]
dateCreated: 2015-10-23
lastModified: 2016-01-12
packagesLibraries: [ ]
category: [self-paced-tutorial] 
tags: [R, GIS-Spatial-Data, metadata-eml, informatics]
mainTag: spatial-data-management-series
description: "Add description here."
code1: 03-metadata-formats-and-files.R
image:
  feature: NEONCarpentryHeader_2.png
  credit: A collaboration between the National Ecological Observatory Network (NEON) and Data Carpentry
  creditlink: http://www.neoninc.org
permalink: R/metadata-file-formats-structures
comments: false
---

{% include _toc.html %}

##About
Add description.

**R Skill Level:** Intermediate - you've got the basics of `R` down.

<div id="objectives" markdown="1">

#Goals / Objectives

After completing this activity, you will:

* Understand that metadata come in many formats and must be maintained with the
data. 
* Understand that there is necessary metadata associated with and/or embedded in
the data.
* Understand that collecting data requires/includes collecting the metadata.
* Be able to create metadata files for different data types. 

##Things You’ll Need To Complete This Lesson
To complete this lesson: you will need the most current version of R, and 
preferably RStudio, loaded on your computer.

###Install R Packages

* **NAME:** `install.packages("NAME")`

* [More on Packages in R - Adapted from Software Carpentry.]({{site.baseurl}}R/Packages-In-R/)

###Download Data

****

{% include/_greyBox-wd-rscript.html %}

**Raster Lesson Series:** This lesson is part of a lesson series introducing
[spatial data and data management in `R` ]({{ site.baseurl }}tutorial/URL).
It is also part of a larger 
[spatio-temporal Data Carpentry Workshop ]({{ site.baseurl }}workshops/spatio-temporal-workshop)
that includes working with  
[raster data in `R` ]({{ site.baseurl }}tutorial/spatial-raster-series),
[vector data in `R` ]({{ site.baseurl }}tutorial/spatial-vector-series)
and  
[tabular time series in `R` ]({{ site.baseurl }}tutorial/tabular-time-series).

****

###Additional Resources

* <a href="http://cran.r-project.org/web/packages/raster/raster.pdf" target="_blank">


</div>

##What is it?

STRUCTURED data describing a dataset
Documents who ‘collected / created’ the data, how, units and data structure, and spatial attributes. 

With spatial data there is information that's necessary to understand it, but usually isn't included in the file.  This is the metadata. Data about the data.

Use a file type. Show the raster of Harvard forest. Ask, what can you say
about this data?

What would you want/need to know about this data to be able to answer questions using this data?

- where is this?
- what coordinate system?
- date?
- time?
- instrument?
- what's being measured?
- what units?

With this file type as is, can you figure any of these things out?

No, you can't figure this out. You need the data about the data. This is the metadata. This information is sometimes embedded in the file (we'll talk about this) or a separate file that contains this information. Sometimes it's in the download directory, but other times, it's just listed on a web site or in another directory and you need to seek it out.

-- show cropland data layer as an example of a data repository that has the metadata on its web site, not when you download it

Metadata comes in many formats, but generally is a text file like txt, CSV or XML.

###Ancillary data

Each element in the file can have more data associated with it. This can be things like a measured time series for an individual point or vector.

This is often things like CSV files. They don't have a spatial element. You have to attach that data to the spatial data information.

There also can be raster or vector data for the same area over time.

All these different data types and series can be combined or compared.

##Why is it useful
Need to document where the data came from and how it was produced
also in the case of structured, digital metadata (e.g. EML) it can be used to automate workflows. For instance, things like scale factors, units, and uncertainty values may be stored in metadata and accessed programmatically to convert / transform data within an algorithm.

##Where to find it? 
location and format will vary by provider. 
best case scenario: packaged with a download in machine readible: txt, xml or eml format, 
Less good: availbale on the website / repo / portal where data were download

##Structured File Formats (very high level):
** provide examples of each of the above - we have that from the harvard met data and the EML file- i can pull XML and a file with a header - the daylength files have a header i think?
###Ecological Metadata Language (EML): XML based format… more here 
eg harvard forest LTER
Code chunk showing some EML
** link out to EML lesson (in NEON-DS-Lesson-Development Repo: {{ site.baseurl }}/R/EML)
###XML - common for GIS ….
Code chunk showing XML
###Web pages with text - EG harvard forest LTER
screen shots?
###HEADERS of text files
eg raster .asc files
** provide examples of each of the above - we have that from the harvard met data and the EML file- i can pull XML and a file with a header - the daylength files have a header i think? 
little activities to go look at metadata…






