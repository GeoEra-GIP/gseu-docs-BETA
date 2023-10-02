# List of terms used in the EGDI documentation

This section contains a description of the terms used in this user guide. Some of the terms (like maps and layers) are in this documentation used in a EGDI specific way to describe features on the portal.

## Data set

A data set is a set of data delivered to EGDI by upload or by service. The data in the data set share the same metadata entry in EGDI's metadata catalogue. Often a data set is shown on the EGDI portal as a single layer on a map. Complex data sets like the Minerals4EU data set can be show as several layers.

## EGDI Metadata Catalogue (MIcKA)

The EGDI Metadata Catalogue - MIcKA - is the central access point to metadata concerning structured digital geological data sources and web services across Europe. In MIcKA you can find metadata about all data sets uploaded to EGDI. Read more about MIcKA here (<https://czechgeologicalsurvey.github.io/MICKA-Docs/mickacookbooklite.html>#).

## GDAL

GDAL is a translator library for raster and vector geospatial data formats that is released under an MIT style Open Source License by the Open Source Geospatial Foundation <http://www.osgeo.org/>

## GeoPackage

A more modern way to exchange spatial data. A GeoPackage is a simple (SQLite) database and can contain several tables. These tables can be used for the thematisation. If the GeoPackage is created using QGIS it is possible store the thematisation in the GeoPackage and reuse this for the thematisation on the EGDI portal (this a new feature and to which extent this is possible is under investigation).

## GeoTIFF

GeoTIFF is a public domain format designed to deliver geocoded maps in a raster based format. GeoTIFF files are often used to place scanned maps in a GIS environment. Compared to [geocoded JPEG](#geocoded-jpeg-2000) GeoTIFF files are much larger but the compression is lossless.

## Grid data

Grid data is often output from a calculation such as a gridded surface. Often a gridded data set only contains a single value for each cell - like the level of topography. These grids are often stored in formats like GeoTIFF.

In some cases a gridded data set contains several values for each cell. This could be data describing a groundwater reservoir where the values could be parameters like thickness, horizontal and vertical hydraulic conductivity. This type of data are often stored in the [NetCDF](#netcdf) format.

## Geocoded JPEG 2000

A geocoded JPEG 2000 is a standard JPEG 2000 formatted image where the geocoding has been added as tags to the images metadata. Compared to [GeoTIFF](#geotiff) JPEG has much better compression but the compression algorithm causes details in the image to be lost.

## Layer

Layers are visualisation of data sets delivered to the EGDI platform. A layer can be as simple as the layer showing the regions of interest on the map above or be an advanced visualisation based on a query on the data delivered.
Map.

## Map

A map on the EGDI portal is a collection of layers grouped in thematic groups like <https://data.geus.dk/egdi/?mapname=egdi_geoera_geoconnect3d>. On the map different layers can be turned on / off, their transparency can be changed and in some cases the content of layers can be filtered.

## Metadata

Data that provides information about spatial and non-spatial data (e.g., purpose of the data, time of creation, authors, etc.).

## MIcKA

See [EGDI Metadata Catalogue (MIcKA)](#egdi_metadata_catalogue_micka).

## NetCDF

A grid data format that can contain multiple values for each cell. These values can be used to describe different parameters describing the same cell or a time component showing the theme of e.g. ice coverage at different times.

## Project vocabulary

A collection of terms with short descriptions, bibliographic citations and links to unstructured web contents used to define scientific parameters and concepts.

## QGIS

QGIS i a Free and Open Source Geographic Information System (GIS). QGIS allows you to create, edit, visualise, analyse and publish geospatial information on Windows, Mac, Linux, BSD and mobile devices.

## Shapefile

Shapefile is a format for storing and exchanging spatial data developed by Esri. The format has been used in many years and has several limitations but can be read and written by a lot of different programmes. A shapefile is not a single file but a collection of files containing different parts of the data. The file ending with .shp contains the geometry features, the one ending with .dbf attributes and the one ending with .shx an index to speed up searching the spatial elements. Shapefiles. Shapefiles should only be used for delivering simple data such as the "Regions of interest” on the GeoConnect3d map.

## Spatial data

The term spatial data is used for data sets that includes spatial information as a point, a line or a polygon. The spatial data can be shown as a layer on a map on the portal. A special form of spatial data are geocoded [gridded data](#grid-data) where each cell in the data set describes a specific square area.

## Unstructured data

Unstructured data can also be delivered to the EGDI portal. This can be pdf documents, picture or data in CSV (comma separated files) format. These data will be made available through links to the EGDI document repository. It is also possible to register an article that is not publicly available but where you need to pay a fee to access the paper. These articles can be registered by their DOI. When these documents are uploaded to the EGDI platform you have to add some metadata about the document.

## Web Feature Service

The Web Feature Service (WFS) is a service to deliver geographical features over the internet. As opposed to the web map service the WFS delivers data in an a XML based format allowing spatial queries and thematisation of the data at the client.

## Web Map Tile Service

The Web Map Tile Service (WMTS) is much like the web map service but in the WMTS all the images are pre created server side to be able to deliver the map fast to many simultaneous users.

## Web Map service

A Web Map Service (WMS) is a service created to deliver georeferenced map images over the internet. The service does not deliver data but an image of data. The service can have an GetFeatureInfo function that can deliver information about a point on the map. The WMS and its related services are the back bone of many web GIS systems.

## Document Details

![GeoERA](../_media/GeoERA.png)

### Report

Authors and affiliation: GEUS

Name(s): MH

Report Name: EGDI Administration Module

Work package: WP6 and WP7

E-mail of lead author: mh@geus.dk

Version: 20/10/2020

This report is part of a project that has received funding by the European Union's Horizon 2020 research  and innovation programme under grant agreement number 731166.

![EU](../_media/EU.jpg)

Report Status: Under development
