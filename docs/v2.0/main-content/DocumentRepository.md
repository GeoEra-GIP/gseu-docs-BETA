# The EGDI Document Repository

The document repository is made as a storage for documents, pictures and comma separated files. When a file is uploaded to the repository it will get a static URL that allows the user to link to the file from other files or from spatial data uploaded to EGDI.

## The EGDI Search Tool

The EGDI Search Tool is made for searching through the data uploaded to the EGDI Document Repository.

The Search Tool is capable of searching through the metadata supplied during upload of the documents and for PDF files also through the documents themselves.

You have three types of search available from the EGDI Search Tool. They are based on multiple keyword search (basic, semantic, advanced) and the spatial search.

All search results will be sorted by the score / weight that is passed from the search engine [Solr](https://lucene.apache.org/solr/) and determines the most relevant results. All search results also have the searched keywords (basic and semantic) highlighted in the results.

Results to the keyword based search will be delivered based on the user's own keywords from the input field or from the predefined list of keywords **populated from the SparQL endpoint (this is not understandable for end users) - is this list a GeoERA or INSPIRE list**.

* Basic search passes the keyword(s) picked by the user to the search engine weighted.
* Semantic search passes the user's determined searched words and adds them the relevant keywords that correspond to the SparQL search (autosuggest & semantic) endpoint, including in all the chosen languages.
* Advanced search will enable the user to combine different search criteria, such as grouping terms, boolean operators (AND, OR, NOT), required and prohibited operators and narrowing down search results to specific fields.
* Spatial search will enable search in combination with the user's interaction with the web map, returning search results based on the criteria if the results fall into the specific rectangle, polygon, etc.

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
