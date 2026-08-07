---
title: Contributing Citations
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/contributing-citations-and-references
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Data repositories play an important role in data citation by linking their data to the articles that cite them. DataCite metadata schema has specific fields that can be populated in order to generate a link between the data and the publication that cites it.

Repositories can contribute citations as follows:


1. Researchers ensure that the associated publications are indicated somewhere in their dataset metadata when it is submitted to the repository OR the repositories detect these links through additional curation work.
2. These links are included in the DataCite metadata (see examples below). There are three fields that should be populated; *relatedIdentifier*, *relatedIdentifierType*, *relationType*
3. Publishers can access this information and link back from the article to the dataset

The graphic below illustrates this workflow:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71d3f25-scholix.png",
        "scholix.png",
        883,
        612,
        "#dbebf2"
      ]
    }
  ]
}
[/block]
This metadata can be added for a DOI you are creating/updating via any of the APIs or the file upload in Fabrica. 

## relationType Metadata Examples

Example 1 JSON metadata of a DOI showing relationType IsReferencedBy
https://doi.org/10.17035/d.2018.0055749445

```json
 ],
  "relatedIdentifiers": [
    {
      "relationType": "IsReferencedBy",
      "relatedIdentifier": "10.3389/fmats.2018.00051",
      "relatedIdentifierType": "DOI"
    }
  ],
```

Example 2 JSON metadata of a DOI showing relationType IsSupplementTo
https://doi.org/10.6084/m9.figshare.7649417.v1

```json
  ],
  "relatedIdentifiers": [
    {
      "relationType": "IsSupplementTo",
      "relatedIdentifier": "10.1159/000496562",
      "relatedIdentifierType": "DOI"
    }
  ],
```

Example 3 JSON metadata of a DOI showing relationType IsCitedBy https://doi.org/10.15128/n583xt96p

```json
  {
      "relationType": "IsCitedBy",
      "relatedIdentifier": "10.1103/physrevlett.115.056601",
      "relatedIdentifierType": "DOI"
    }
  ],
```


Data citation information is then made openly available via Event Data so that anyone interested can find and use this information. [To learn about EventData, read the Event Data guide](doc:eventdata-guide)