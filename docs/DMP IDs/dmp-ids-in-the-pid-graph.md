---
title: DMP IDs in the PID Graph
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
The relations in the metadata associated with PIDs have the potential to enable a connected research graph. These relations are stored in DataCite Event Data and made available via the [DataCite Graph QL API](doc:datacite-graphql-api-guide). When DataCite DMP IDs include links to other related PIDs, it becomes possible to display DMP statistics, for example, for an organisation, funder and/or data repository. 

A complete [guide to using Jupyter notebooks to display connections between DMPs](https://mybinder.org/v2/gh/datacite/pidgraph-notebooks-python/master?urlpath=lab/tree/dmp)  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45fd8d7-Screen_Shot_2021-03-31_at_11.17.29.png",
        "Screen Shot 2021-03-31 at 11.17.29.png",
        1640,
        914,
        "#f9f9f8"
      ],
      "caption": "Figure 1: Visualization of the connections between a DMP and related datasets, publications, funders, organizations and people."
    }
  ]
}
[/block]