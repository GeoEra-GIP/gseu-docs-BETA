# General Introduction

When a project decides how to deliver data to the EGDI platform there
are several aspects that must be considered.

First the project has to choose to deliver the different data sets by
either upload or by services. The projects must be aware that if they
choose to deliver as services the partners of the project must be
committed to keep these services up and running and updated according to evolving standards at least five years after the end of the project.

If the data set consist of data only collected during the lifetime of the project the best option is to upload to the EGDI platform on the GeoPackage format or as a Shapefile (if the content of
the data set is simple). If it is chosen to deliver data by upload the project must harmonise (and standardise) the data within their project, and preferable deliver the data as on GeoPackages / Shapefile.

When you decide how to deliver the data sets you must also take into account that the way the data are delivered has effect on the functionality on the platform seen from a user perspective. The data uploaded to the platform will be available as long as the platform is running. Data uploaded to the platform will be stored in EGDI's internal database and can be used in more advanced visualisation, filtering and searching. If data are delivered by several partners the up-time of the whole data set becomes an issue as the services must up an running at all the partners for the data set to fully. If for example all partners have an up-time of 95%.

## Delivering Spatial Data by upload

GeoPackages are preferred for harmonised data as the standardised code lists often have column headings that cannot fit into a shapefile. It is also possible to define the thematisation in a GeoPackage. This thematisation can in many cases be used directly by the EGDI platform. Shape files on the other hand are fine for simpler data set as the location of pilot areas investigated during a project, location of pictures etc.

We recommend to use GeoPackages for the following reasons:

* GeoPackages is a modern format for spatial data based on SQLLite
* All data are contained in a single file
* Can contain several spatial tables
* Can contain thematisation of the layers (can only be made using QGIS and EGDI only support simple thematisation)
* Can be downloaded from EGDI ready to use by the end users in GIS applications

if you have a Shapefile you can convert it to a GeoPackage using the GDAL tool ogr2ogr (part of a QGIS installation or downloadable from www.gdal.org):

```txt
\OSGeo4W\bin\ogr2ogr.exe -f GPKG conv.gpkg TestShapefile.shp
```

ogr2ogr has a lot of functionality to manipulate the data during the conversion for a complete reference se here <https://gdal.org/programs/ogr2ogr.html>.

This will convert the TestShapefile.shp to a GeoPackage called conv.gpkg. Note that til will not contain the thematisation at this is not a part of the Shapefile.

If the data set will be modified after the end of the project it can be chosen to update the GeoPackage at intervals or to deliver the data through a service.

Another factor the project needs to consider when choosing how to deliver their data is the usability of the data set on the platform. Data uploaded to the platform will be loaded into the central database and can be combined with other data uploaded to the platform - also data uploaded by other projects. In this way it is possible to filter data from one data set based on information's from another.

It is also possible to combine data where one part of the data is delivered by GeoPackages / Shapefile and another part of the data are delivered by services. An example where this is done is by the TACTIC project where  locations of boreholes with online monitoring of the groundwater level are delivered as a shapefile while the online measurements of water levels are delivered by a REST service. From these boreholes it will be possible to see and access the online water levels measurements directly from the data provider.

Data can be delivered in other formats but that must be agreed upon between the GSP and the GIP-P. For example, it has been decided to deliver grids with multiple cell values in the NetCDF format.

Before uploading spatial data or registering services to deliver data to the EGDI platform, the metadata must be entered into the EGDI metadata catalogue <https://egdi.geology.cz/>. A link to the metadata entry describing the data set / service / model is mandatory when adding data / services / models to the EGDI platform. **The user cannot commit the upload unless adding a link to the metadata record**. See [Uploading data to EGDI](/main-content/AdministrationModule.md) for more information's.

The detailed guidelines how to proceed are available at Cookbook
([https://czechgeologicalsurvey.github.io/MICKA-Docs/mickacookbooklite.html\#](https://czechgeologicalsurvey.github.io/MICKA-Docs/mickacookbooklite.html) )
and at EGDI Metadata Profile detail description
([https://czechgeologicalsurvey.github.io/MICKA-Docs/EGDIProfile.html\#](https://czechgeologicalsurvey.github.io/MICKA-Docs/EGDIProfile.html)).

Do you need more information on how to upload metadata? Contact us on email [metadata.egdi@geology.cz](mailto:metadata.egdi@geology.cz)

It is up to the project to harmonise the data and delver the data from different partners as one data set.

### Searching

The EGDI platform will be able to search through the database that holds the data uploaded to the platform. In this way data delivered by GeoPackages or Shapefiles can be found through their metadata (stored in the EGDI metadata catalogue) but also through the data content. Data delivered by services can only be found through their metadata.

### Availability

Besides being shown on the EGDI platform, all spatial data delivered to the EGDI platform can be made available through WMS and WFS services when the map layer is defined and thematised during upload of the GeoPackage / Shapefile. The data will also be available for download.

## Delivering data by services

If you decide to deliver data by services EGDI can use the following types of services:

* Web Map Services (WMS)
* Web Feature Services (WFS)

Data delivered to the platform by services can in special cases be harvested by the platform. Harvesting is most relevant in cases where a data set has many partners delivering parts of it. The Minerals4EU data is an example where many partners deliver data to the platform and where the experience has shown that in order to show a coherent data set for all of Europe these different sub data sets need to be consolidated into one.

### Searching

The user will be able to find the data through their metadata (stored in the EGDI metadata catalogue MIcKA).

### Availability

The availability of the data set will rely on the availability of the service / services running at the partners.

## Delivering unstructured data

Several projects want to deliver unstructured data such as documents (with or without spatial reference), pictures / images and tabular data.

For these data a document repository has been developed. It is possible to upload / register the following types of unstructured data to the EGDI platform:

* PDF files
* DOI reference to documents
* Pictures (png, jpg, jpeg)
* Tabular data in CSV format

The repository is intended to store files that the different projects want to make available for the end users. The files uploaded to the repository can be made available from the EGDI Web GIS through links to the file. The content of the files with tabular data will not be imported into the EGDI database and cannot be used in combination with the other data in the database.

Metadata for unstructured data are stored in the central EGDI database (not in the EGDI Metadata Catalogue as metadata for spatial data and services are). These metadata include title, author, keywords, abstract, (spatial extent). The possible metadata types will differ for the different types of data. Where possible the metadata will be extracted from the uploaded file (relevant for PDF files and pictures) and the user will be able to add and change the different metadata elements.

All the files uploaded to the document repository will return a URI (a static URL) that can be used to refer to the file. All files uploaded to the repository can be accessed through a homepage where all files of the different types can be listed. This list can be filtered by project, file type etc. For users logged into the EGDI administration module it will also be possible to edit the metadata / delete files.

### Searching

The EGDI search system will be able to search through the metadata for all files uploaded to the platform. If PDF files are readable also the content of the files searched. If the uploaded file has been geocoded they can also be found based on their location. If a document is registered through a DOI only its metadata can be searched (these metadata can contain its location).

### Availability

Besides being available through the platform all files uploaded to the platform will be available through an URL. You will get this URL when the document has been uploaded.

## Delivering 3D models

Another type of data that can be stored on the platform are 3D models. Given the lack of a standard exchange format for 3D models that the different modelling tools can import / export the data have to be exported from the modelling tools and uploaded to the EGDI platform in ASCII formats. Currently the following formats are supported:

1. Raster file formats
   * \*.asc
   * \*.grd
2. Tin file formats
   * \*.obj
   * \*.ts
3. Voxel file formats
   * \*.xyz

These formats make it is possible to (at least) import models developed in GoCAD, LeapFrog, Petrel and GeoScene3D. The list of formats from which a model can be imported from and exported to will be expanded with time.

When you deliver the model you must deliver each layer / body in separate files and include description of the layers.

The models will be stored in the EGDI 3D model database (based on the 3D Model Database developed by GEUS). The models can be visualised on the platform and are made available through a set of REST services (the same services that are used by the visualisation tool).

### Searching

3D models can be found through their metadata.

### Availability

Besides being shown and visualised on the EGDI platform, models uploaded to the platform can be downloaded in the same format in which they have been uploaded. The models will also be available through a REST service (user for the visualisation tool). The list of formats in which the models are made available will most probably be expanded with time.

## Document Details

![GeoERA](../_media/GeoERA.png)

### Report

Authors and affiliation: GEUS

Name(s): MH

E-mail of lead author: mh@geus.dk

Version: 20/10/2020

This documentation is part of a project that has received funding by the European Union's Horizon 2020 research  and innovation programme under grant agreement number 731166.

![EU](../_media/EU.jpg)

Report Status: Under development
