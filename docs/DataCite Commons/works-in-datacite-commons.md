---
title: Works in DataCite Commons
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: connections-in-datacite-commons
      title: Connections in DataCite Commons
---
## Search Works

Use the Works tab in DataCite Commons to search through the metadata catalogue of all DataCite DOIs in Findable state as well as a large number of Crossref DOI metadata. To start, enter a search term in the search bar at the top of the page.

### Filtering

The results list can be modified using the following filters:

- Creators & Contributors
- Publication Year
- Work Type (using the DataCite ResourceTypeGeneral controlled List)
- License (using the [SPDX](https://spdx.org) controlled vocabulary)
- Language (using the [ISO639-1](https://www.iso.org/iso-639-language-codes.html) controlled vocabulary)
- Registration Agency (one of the eight DOI Registration Agencies for scholarly content)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c517e5-commons_works_search.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 📘 Search queries
> 
> Queries by default search the DOI, relatedIdentifier, title, creator, publisher, description, and subject fields. Using advanced queries, specific fields can also be queried as well, e.g. <https://commons.datacite.org?query=publicationYear:2016>. Some of the advanced features are described with examples in the [Querying DataCite Commons documentation](doc:datacite-commons-search).

### The DOI record

The full DOI record includes information from the metadata file including the title, resource type and language. There are up to 5 tabs which contain information about the description, other identifiers, creators, contributors and registration.

On the left panel the "Add to ORCID Record" button appears at the top. Click here to claim the DOI record and [link it to your ORCID profile](doc:orcid-claiming). The "Download Metadata" button also appears on the left. Click here to download the full metadata record in DataCite XML, DataCite JSON, schema.org, JSON LD or to retrieve the citation in Citeproc JSON, Bibtex and RIS formats. Crossref DOIs with Open Access content available via the [Unpaywall](https://unpaywall.org/) API will display a link to the fulltext article. 

> 📘 A note on ORCID Claiming
> 
> To manually link a DOI record to an ORCID record, you must be logged into DataCite Commons with your [DataCite Profiles](doc:datacite-profiles-user-documentation) account. Click on the "Add to ORCID Record" button that appears in the DOI record. Refer to the [ORCID Claiming documentation](doc:orcid-claiming) for more information.

Information about the relevant [Creative Commons](https://creativecommons.org/) licenses is also displayed at the top. Click on the license icon to link to the corresponding Creative Commons license page.

![](https://files.readme.io/12811f7-Screen_Shot_2023-03-15_at_09.10.12.png "Screen Shot 2023-03-15 at 09.10.12.png")

### Views, Downloads and Citations

For works where the hosting repository has submitted usage reports to DataCite, monthly unique views and downloads are displayed at the top of the DOI record. Citations related to the DOI are also displayed at the top.

![](https://files.readme.io/2485a1b-Screenshot_2023-03-15_at_16.48.43.png "Screenshot 2023-03-15 at 16.48.43.png")

> 📘 Citations
> 
> A citation will only appear in the DOI record if the DOI metadata includes the relatedIdentifier following the guidelines outlined in the [citations and references documentation](https://support.datacite.org/docs/citations-and-references).

Aggregated information about the Publication Year, Work Types and Licenses of the related references and citations is displayed at the bottom of the full DOI record.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/300bcdd-commons_works_related.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 📘 Creators and contributors display
> 
> There is an upper limit of 20 creators or contributors that can be displayed in DataCite Commons for a DOI record. Some records have very large numbers of creators/contributors, so it is necessary to set a limit for display purposes. 
> 
> The full metadata record can be downloaded in JSON and XML or [retrieved via our API](ref:get_dois-id).