---
title: What are the sources of citation information in DataCite services?
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Citations and references are links between research outputs. DataCite ingests these links and provides services to allow you to [see the number of times your research outputs with a DataCite DOI have been cited](doc:consuming-citations-and-references). There are two ways that DataCite ingests citation information:

1. The [relatedIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4.7/properties/relatedidentifier/) property appears in DataCite DOI metadata with a [relationType](https://datacite-metadata-schema.readthedocs.io/en/4.7/properties/relatedidentifier/#b-relationtype) for a citation or reference:
   1. Primary DOI includes citation relationType (IsCitedBy/IsReferencedBy/IsSupplementTo) in the relatedIdentifier, this creates one citation for the primary DOI.
   2. Primary DOI includes reference relationType  (Cites/References/IsSupplementedBy)in the relatedIdentifier, this creates one citation for the other DOI.

Find out more about [contributing citations and references](doc:contributing-citations-and-references).  

2. The data citation endpoint from Crossref:
   1. The [Crossref data citation API endpoint](https://www.crossref.org/documentation/retrieve-metadata/data-citations/) provides access to data citation relationships (links between articles and datasets) deposited by Crossref members. It features connections to datasets with either Crossref or DataCite DOIs.