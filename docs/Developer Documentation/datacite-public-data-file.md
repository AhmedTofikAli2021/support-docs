---
title: DataCite Public Data File
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
## About the DataCite public data file

The DataCite public data file contains metadata for all publicly available DataCite DOIs.

All metadata contained in the file is freely available under a CC0 waiver. For more information, see the [DataCite Data File Use Policy](doc:datacite-data-file-use-policy).

DataCite’s first public data file (released in March 2024) contains metadata for 52,863,283 DOIs that were registered up to the end of 2023. Going forward, DataCite will release public data files annually.

## Accessing the public data file

Access the public data file at <https://datafiles.datacite.org/>. This portal lists all available public data files and provides direct download access.

## Contents of the public data file

The public data file contains JSON metadata for all DataCite DOIs in [Findable state](doc:https://support.datacite.org/docs/doi-states#findable-doi-name). 

The metadata is available within a gzipped tar file. Inside this file, individual records are grouped into folders by DOI prefix. Each prefix folder contains a set of JSON files, comprising up to 1,000 records each.

For the initial release, the gzipped tar file is approximately 24 GB (compressed) and 211.5 GB uncompressed.

## Using the public data file

As the public data file contains metadata for all Findable DataCite DOIs, it can be used to seed an initial harvest of DataCite DOI metadata.

For newly registered DOIs and updates to existing DOI metadata, the [DataCite REST API](doc:api) can be used to [retrieve a list of DOIs](doc:api-get-lists). The results can be sorted and filtered by the last updated date.  For example:

- Sort by date updated (newest to oldest): `https://api.datacite.org/dois?sort=-updated`
- Filter by date updated and sort oldest to newest: `https://api.datacite.org/dois?sort=updated&query=updated:[2024-01-01 TO 2024-01-31]`