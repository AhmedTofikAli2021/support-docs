---
title: DataCite Commons
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
Access DataCite Commons at [https://commons.datacite.org](https://commons.datacite.org).

# Introduction

DataCite Commons describes works, people, and organizations, and their connections and allows users to search for them. They are identified by persistent identifiers (PIDs): works (DOI), people (ORCID ID), and organizations (ROR ID), and have standard metadata that describe them and the connections to each other. Together they form the [PID Graph](https://doi.org/10.5438/jwvf-8a66), which is powered by the [DataCite GraphQL API](https://support.datacite.org/docs/datacite-graphql-api-guide). DataCite Commons provides a public web search interface to the PID Graph.

DataCite Commons is work in progress as part of the European Commission-funded [FREYA](https://www.project-freya.eu/en) project with a first public version released in August 2020, with 30 million works, nine million people and 100,000 organizations. DataCite Commons was officially launch in October 2020.

# Search

DataCite Commons provides a single search interface for **Works**, **People**, and **Organizations**. Works are content registered with a DOI from DataCite, Crossref, or one of the other six scholarly DOI registration agencies. The **People** search integrates with the [ORCID](https://orcid.org) API and the **Organizations** search integrates with the [ROR](https://ror.org) API. When on a page that lists works (person, organization or references and citations for a work), there is also a **This Page** search option.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a82fd14-search-box.png",
        "search-box.png",
        750,
        264,
        "#f9fbfc"
      ],
      "caption": "Search box at https://commons.datacite.org/ror.org/00k4n6c32."
    }
  ]
}
[/block]
## Search Works

DataCite Commons supports exactly the same queries as [DataCite Search](https://support.datacite.org/docs/datacite-search-user-documentation) and [DataCite Fabrica](https://support.datacite.org/docs/doi-fabrica). Under the hood these are all [query string queries](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html) from Elasticsearch. Some of the advanced features are briefly described below.

### Field names
Queries by default search all fields, but a specific field can be provided in the query, e.g. https://commons.datacite.org?query=publicationYear:2016

For nested fields use the same format as in the REST API response, e.g. https://commons.datacite.org?query=creators.nameIdentifiers.nameIdentifierType:ORCID

### Wildcards
Wildcards are supported, e.g. https://commons.datacite.org??query=creators.familyName:mil*

### Boolean operators
By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example https://commons.datacite.org?query=titles.title:climate%20+change

### Ranges
For number and date fields, we can specify a range. Wildcards are supported e.g. [https://commons.datacite.org?query=publicationYear:[2019%20TO%20*]](https://commons.datacite.org?query=publicationYear:[2019%20TO%20*] ) or [https://commons.datacite.org?query=view_count:[1000%20TO%201999]](https://commons.datacite.org?query=view_count:[1000%20TO%201999]) 

### Filtering
You can modify your search by using the following filters:

* Publication Year
* Work Type (using the DataCite ResourceTypeGeneral controlled List)
* License (using the [SPDX](https://spdx.org) controlled vocabulary)
* Language (using the [ISO639-1](https://www.iso.org/iso-639-language-codes.html) controlled vocabulary)
* Field of Science (using the [OECD Fields of Science](https://www.oecd.org/science/inno/38235147.pdf) controlled vocabulary)
* Registration Agency (one of the eight DOI Registration Agencies for scholarly content)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1299d9-Bildschirmfoto_2020-08-25_um_11.02.25.png",
        "Bildschirmfoto 2020-08-25 um 11.02.25.png",
        2796,
        1258,
        "#f4f6f8"
      ],
      "caption": "Search for works by keyword COVID-19, filtered by license CC-BY 4.0. https://commons.datacite.org/doi.org?query=covid-19&license=cc-by-4.0"
    }
  ]
}
[/block]
## Search People
For searching people, DataCite Commons uses the ORCID API and its query options described [here](https://members.orcid.org/api/basic-tutorial-searching-data-using-orcid-api-30). This includes support for field names and boolean operators as described above.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47314c7-Bildschirmfoto_2020-08-25_um_11.10.14.png",
        "Bildschirmfoto 2020-08-25 um 11.10.14.png",
        2046,
        1200,
        "#fbfcfc"
      ],
      "caption": "Search for people by name and keyword. https://commons.datacite.org/orcid.org?query=John%20Smith%20Edinburgh"
    }
  ]
}
[/block]
## Search Organizations
For searching organizations, DataCite Commons uses the ROR API and its query options. The ROR API also uses [query string queries](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html) from Elasticsearch, and the query options are similar as for searching works.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d967e62-Bildschirmfoto_2020-08-25_um_10.58.34.png",
        "Bildschirmfoto 2020-08-25 um 10.58.34.png",
        2206,
        1224,
        "#f9fbfc"
      ],
      "caption": "Organization keyword search with filtering by country. https://commons.datacite.org/ror.org?query=Lincoln+University&country=us"
    }
  ]
}
[/block]
# Connections

DataCite Commons shows the following connections:

* Works: references, citations, views, and downloads
* People: works
* Organizations: works

The references and citations, shown for works come via related identifier information from DataCite and Crossref DOI metadata.

The views and downloads shown for works come via usage reports following the [COUNTER](https://www.projectcounter.org/) standard submitted from repositories to DataCite.

The works shown for people come via creator name identifier information from DataCite and Crossref DOI metadata.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/afe52d6-Bildschirmfoto_2020-08-25_um_10.57.14.png",
        "Bildschirmfoto 2020-08-25 um 10.57.14.png",
        2646,
        1286,
        "#f9fbfb"
      ],
      "caption": "Works by person with summary statistics https://commons.datacite.org/orcid.org/0000-0003-3484-6875"
    }
  ]
}
[/block]
The works shown for organizations come via affiliation and funding information (using ROR and Crossref Funder Identifier) from DataCite and Crossref DOI metadata. If the ROR ID is included in the DataCite organizational profile, all of the works linked to that organization will be displayed in DataCite Commons as well.

## Listing works

Listings of works (whether references, citations, or works associated with a particular person or organization) come in a standard format and allow queries, filtering, and pagination. They also display the following summary statistics:

* Works by publication year
* Works by work type
* Works by license
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6423f93-Bildschirmfoto_2020-08-25_um_06.35.32.png",
        "Bildschirmfoto 2020-08-25 um 06.35.32.png",
        1900,
        1366,
        "#f9fbfb"
      ],
      "caption": "Aggregate statistics for works by funder at https://commons.datacite.org/ror.org/00yjd3n13."
    }
  ]
}
[/block]
## Showing Views and Downloads

For works where the hosting repository has submitted usage reports to DataCite, we show monthly unique views and downloads. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4acb632-aggregatedworks.jpg",
        "aggregatedworks.jpg",
        1547,
        648,
        "#f7f9f9"
      ],
      "caption": "Views, downloads and citations for dataset https://commons.datacite.org/doi.org/10.5061/dryad.234"
    }
  ]
}
[/block]

# Login

Using the [DataCite profiles](https://support.datacite.org/docs/datacite-profiles-user-documentation) service you can login e.g. with your ORCiD, to the Commons service to add additional functionality.

One of the advantages to login is being able to see your claimed ORCiD works.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7cb6270-orcidclaimscommons.jpg",
        "orcidclaimscommons.jpg",
        1602,
        1082,
        "#f7f9f9"
      ]
    }
  ]
}
[/block]
# Statistics

From the [statistics page](https://commons.datacite.org/statistics) you can find a live summary of the data involved in the PID Graph.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a45fc68-commonsstatistics.jpg",
        "commonsstatistics.jpg",
        1085,
        529,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
**This work was funded as part of the FREYA project. The FREYA project has received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement No 777523.**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f53f45e-d5c4d09-Screen_Shot_2020-04-09_at_14.05.39.png",
        "d5c4d09-Screen_Shot_2020-04-09_at_14.05.39.png",
        200,
        120,
        "#f0f3ef"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e7c4cb9-8eb07cb-Screen_Shot_2020-04-09_at_14.10.22.png",
        "8eb07cb-Screen_Shot_2020-04-09_at_14.10.22.png",
        200,
        134,
        "#133b92"
      ]
    }
  ]
}
[/block]