# FAQ

Here we will add frequently asked questions.

## How do I replace a pdf that I have uploaded earlier without changing the UrI?

It is possible to reupload and overwrite the existing file and keeping the URI from the first upload. When reuploading documents the filename is very important as this will be part of the URI. During upload some characters (like spaces and special characters) that are not URL friendly will be changed. So if you download your document edit it and reupload it, its file name might have changed. The best way to avoid this kind of troubles is to avoid special characters like -, +, ' ', æ, ø, å and so on in the file names.

## I have problems with upload of GeoTIFF files

GeoTIFF does not include a strictly defined format for the projection and in some cases the administration module cannot decifer the projection.

To see if the metadata describing the projection are strictly enough described in the file. You can use a tool like gdalinfo from [GDAL library](https://gdal.org/).

If your GeoTIFF fails on upload you can check the spatial information in the file using the following command:

```text
gdalinfo name-of-geotiff
```

The GeoTIFF should have a metadata structure like the one below where it is clearly defined that the projection is using EPSG 3034 as it does in below:

![GeoTIFF with correct metadata](../_media/AdminModule/media/GdalifoOk.png)

If the metadata in your GeoTIFF like the below:

![GeoTIFF with correct metadata](../_media/AdminModule/media/GdalifoError.png)

As you can see both GeoTIFF hve the same projection as the first tag in in the PROJCRS block, but it is described in text (and not written in the same way). Only the last one have a clear definition of the projection in ID tag (EPSG 3034).

This can be fixed i QGIS by opening the GeoTIFF setting the projection to EPSG 3034 and exporting it to a new file. In ArcGIS the same can be done by resampling and selecting the coordinate system like below:

![GeoTIFF with correct metadata](../_media/AdminModule/media/ArcGISCoorSys.png)

### Saving GeoTIFF from ArcMap

If you are using ArcMap you can your GeoTIFF with the correct metadata format by following this procedure:

* Create a project using a MXD in the correct coordinate system (EPSG:3034)
* Drag your GeoTIFF into the project
* Store the metadata about the projection in the GeoTIFF by using:
  * Georeferencing
  * Rectify...

![Save GeoTIFF from ArcMap](../_media/AdminModule/ArcMapSaveGeoTIFF.png)

## Adding INSPIRE compliant metadata to your data sets

The team behind the EGDI Metadata Catalogue have provided a cook book, a faq and training videos about how to do this. You find this material here:

[MIcKA Documentation](https://egdi.geology.cz/catalog/micka/docs).

## My GeoPackage cannot be uploaded to EGDI

We have seen that some GeoPackages cannot be uploaded to EGDI. These GeoPackages include a z-dimension which EGDI currently not support. To se if this is the problem with your GeoPackage open the GeoPackage from SQLiteStudio and see in the gpkg_geometry_columns table. If it looks like this with zeros in the z and m columns:

![GeoPackage without a z-dimension](../_media/AdminModule/media/GeoPackageWithOutZ.png)

It will work. If it has a z-dimension it will look like this:

![GeoPackage with a z-dimension](../_media/AdminModule/media/GeoPackageWithZ.png)

It will not work.

## Should we deliver one data set for each pilot area or for each type of data?

There is no simple answer to this question. If you have smaller and very separate pilot areas, we suggest that you create one map on which you show your pilot areas and separate maps for the pilot areas.

The data set for the map with the location of the pilot areas can be delivered as one shapefile og a GeoPackage with one spatial theme with polygons showing pilot areas. This theme could contain the following fields:

* geom - holding the polygons for each pilot area
* title - holding the name of the pilot area
* description - holding a short description of pilot area
* repositoryurl - holding a link to a pdf in the document repository with a more extensive description of the pilot area
* mapurl - holding a link to a map defined for each pilot area

Them pilot area specific maps can be defined så that they zoom into the area of the pilot are. It can show the same them with the outline of the pilot area and data specific data sets.

When the project area grows and cover larger part of Europe it becomes more relevant to combine the data set from the different areas into one data set for each type of data.

As a rule of thumbs combine the data sets based on the type of data if it makes sense to show the theme on on one map. If the data sets are to far apart or covering too small areas to be able to seen the on one map then deliver them as pilot are specific data sets.

## Should a project deliver data as one GeoPackage or one for each partner?

In EGDI there is a connection between a data set and a [GeoPackage](/main-content/ListOfTerms#geopackage). So if you want the data set to appear as one data set / layer on the platform you should deliver the data as one GeoPackage. To make it easier to update the GeoPackage you should add an identifier to each spatial element in the GeoPackage that refers to the institution / country delivering this element. In this way you can easily replace all elements from one partner with updated ones. When you register the data set in the EGDI Metadata Catalogue the metadata entry for the whole data set and the metadata entry for the specific partner must be updated.

## We have a geological model should we deliver the layers as a model or on the NetCDF format?

If your model consist of gridded layers (a 2.5D model) you can do both. The difference is how the model can be visualised on the EGDI platform. If you deliver the layers in a NetCDF the different layer can be shown as individual layer on the web GIS. If you deliver the model as a model and it is loaded into the EGDI 3D Model Database the model can be visualised in EGDI's the 3D viewer.

## Which formats does EGDI support?

The EGDI platform can handle spatial data sets, 3D models and unstructured data.

Spatial data containing points, lines or polygons can be delivered as [GeoPackage](/main-content/ListOfTerms#geopackage) or [Shapefile](/main-content/ListOfTerms#shapefile) spatial data in grid / raster formats can be delivered as [NetCDF](/main-content/ListOfTerms#netcdf), [GeoTIFF](/main-content/ListOfTerms#geotiff).

EGDI also support use of [NetCDF](https://www.unidata.ucar.edu/software/netcdf/) files for grid data with multiple values for each cell. It is however not possible to deliver this type of files through the Administration Module. They must be sendt directly to Jørgen Tulstrup and Martin Hansen at GEUS.

For unstructured data, documents can be delivered as PDF files and reference by DOI, pictures as JPEG and PNG files and tabular data as CSV files.

3D models can be delivered in the [formats described here](/main-content/AdministrationModule#uploading-3d-models)

## Document Details

![GeoERA](../_media/GeoERA.png)

### Report

Authors and affiliation: GEUS

Name(s): MH

Report Name: EGDI Administration Module

Work package: WP6 and WP7

E-mail of lead author: mh@geus.dk

Version: 10/08/2021

This report is part of a project that has received funding by the European Union's Horizon 2020 research  and innovation programme under grant agreement number 731166.

![EU](../_media/EU.jpg)

Report Status: Under development
