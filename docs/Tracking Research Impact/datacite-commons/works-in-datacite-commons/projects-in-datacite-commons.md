---
title: Projects in DataCite Commons
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
When a DataCite DOI is registered for a project, the record will be presented on DataCite Commons in the form of a project dashboard.

# Search projects

Use the Works tab in DataCite Commons to search the metadata catalog of all DataCite DOIs in Findable state, including DOIs for projects. To start, enter a search term or query in the search bar at the top of the page.

## Project facets

On the search result page, check the “Project” check box in the “Work Type” facets on the left column to see all search term related projects. This uses the  parameter `resource-type` to define the search, for example: <https://commons.datacite.org/doi.org?query=*&resource-type=project>. Results will include:

- All DOIs with the resourceTypeGeneral “Project”
- All DOIs with “Project” as the free text “resourceType”, in combination with  resourceTypeGeneral“Text” or “Other”

The “Work Type” section contains the top 10 most frequent resource types in the result, so it’s possible that “Project” falls out of scope. In this case, use [advanced search queries](https://support.datacite.org/docs/datacite-commons-search) to find DOIs based on the resource type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1c16b82520503805c75d71e7d42b422a4a8577ea7a0ef2d708bcebb055e66e7-image9.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


# The project record

The project dashboard page retains the [features of the DOI record page of other work types](https://support.datacite.org/docs/works-in-datacite-commons) and provides additional features specific to projects.

## Download Reports

This feature adds a link to the dashboard, allowing users to download a .csv file containing a list of all Related Works. The list includes descriptions and formatted citations in APA style for up to 200 DOIs associated with the project.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1a18908787e03059397a9a4cb25a115f6042d0444ea939bd45f68670a7b615b-image1.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Network Graph

This feature generates a force-directed graph that provides a high-level overview of the different types of works connected to a project and the number of connections between them. The network graph visualizes two-step connections: not only between the project and its related works but also between the related works themselves. 

This visualization is based on the metadata of the DOIs of the project and all works linked to it through metadata:

- Connections are captured via the [relatedIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4.5/properties/relatedidentifier/#) metadata of the both the project DOI and the relatedIdentifier metadata of the DOIs of the related works.
- All [relation types](https://datacite-metadata-schema.readthedocs.io/en/4.5/properties/relatedidentifier/#b-relationtype) are captured, not just the [citation relation types](https://support.datacite.org/docs/contributing-citations-and-references).
- Works are grouped by resource type – based on the [resourceTypeGeneral](https://datacite-metadata-schema.readthedocs.io/en/4.5/properties/resourcetype/#a-resourcetypegeneral) metadata of each work DOI.

View the example project DOI in DataCite Commons: <https://commons.datacite.org/doi.org/10.60581/zaev-6p15> 

> 📘 
> 
> The project DOI is included in the corpus of all works in the graph shown below in the "projects" node.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4236adcaff15cd7874bd3e515c21ca0cca195ac6ae49a9b4dea7aed017606ddc-image7.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Related Works List and Connection Type Facets

The Related Works list contains all works that are associated with the project DOI in the metadata, sorted into the following bins (shown as facets in the left column): 

| Connection Type                                                                       | Description                                                                                                                                                                           |
| :------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| All                                                                                   | Works related to the project through RelatedIdentifier metadata with any [relationType](https://datacite-metadata-schema.readthedocs.io/en/4.5/appendices/appendix-1/relationType/) . |
| [Citations](https://support.datacite.org/docs/contributing-citations-and-references)  | Works that cite the project.                                                                                                                                                          |
| [References](https://support.datacite.org/docs/contributing-citations-and-references) | Works that the project references.                                                                                                                                                    |
| Parts                                                                                 | Works that are part of the project.                                                                                                                                                   |
| Is Part Of                                                                            | Works that the project is part of.                                                                                                                                                    |
| Other                                                                                 | Works that are related to the project in a different way.                                                                                                                             |

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6341d0b41a237fa1cff48e1fe9d90260786401f49eb0cad573c231e8b6b7077d-image6.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Contributions chart

This feature showcases the top contributors to the project and how they contributed to the main types of outputs of the project. The Sankey chart shows two columns: person on the left, work type on the right. It visualizes the number of times each person is associated with each work type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/14ed6d10aa294fb0796ea9d21f475232402f8b8b813cb02775e44cfd62035222-image10.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


# Acknowledgment

The project dashboard is developed as part of the [Implementing FAIR Workflows project](https://doi.org/10.60581/zaev-6p15) funded by the [Templeton World Charity Foundation](https://ror.org/00x0z1472). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c24424a4371c58a4ea83b1587299f813f27f7ff39c0dc751c98735b18dc804be-image5.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "250px"
    }
  ]
}
[/block]


This project was made possible through the support of a grant from Templeton World Charity Foundation, Inc. The opinions expressed in this publication are those of the author(s) and do not necessarily reflect the views of Templeton World Charity Foundation, Inc.