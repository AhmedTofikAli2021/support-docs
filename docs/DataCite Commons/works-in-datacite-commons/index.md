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
---
## Search Works

Use the **Works** tab in DataCite Commons to search through the metadata catalogue. Enter a search term in the search bar at the top of the page. 

Run a [keyword search in the works tab in DataCite Commons](https://commons.datacite.org/doi.org?query=climate+change).

### Scope

DataCite Commons includes all DataCite DOIs in [Findable](https://support.datacite.org/docs/doi-states#findable-doi-name) state.

Crossref DOIs appear in DataCite Commons based on the following criteria:

- A [Scholix](https://www.eventdata.crossref.org/guide/app-scholix/) relationship to a DataCite DOI (i.e., a relationship between literature and a dataset) appears in Crossref event data
- A relationship to a Crossref DOI is detected in DataCite RelatedIdentifier metadata

Crossref DOIs that do not meet these criteria and DOIs from other DOI registration agencies may also appear in Commons due to historical import patterns.

### Filters

The results list can be modified using filters:

- **Creators & Contributors**
- **Publication Year**
- **Work Type** (using the DataCite resourceTypeGeneral controlled list)
- **License** (using the [SPDX](https://spdx.org) controlled vocabulary)
- **Language** (using the [ISO 639-1](https://www.iso.org/iso-639-language-codes.html) controlled vocabulary)
- **Field of Science** (using the subject scheme from [OECD Fields of Science and Technology (FOS)](https://web-archive.oecd.org/2012-06-15/138575-38235147.pdf))
- **Registration Agency** (from the DOI Foundation [DOI Registration Agencies](https://www.doi.org/the-community/existing-registration-agencies/))
- **Repository** (the name of the Repository in DataCite)
- **Repository Type** (corresponding to the [DataCite Repository Type](https://support.datacite.org/docs/update-repository-settings#type) where DataCite DOIs are stored)

> 📘 Search queries
> 
> Queries by default search the DOI, relatedIdentifier, title, creator, publisher, description, and subject fields. Using [queries](doc:queries), specific fields can be queried as well, for example: <https://commons.datacite.org?query=publicationYear:2016>.

## The Work (DOI) Metadata Record

Check out a [DOI record in DataCite Commons](https://commons.datacite.org/doi.org/10.24381/cds.9d44a987).

The full DOI record includes information from the DOI metadata record including the title, description, resource type and language. The tabs display other information from the DOI metadata record about the creators, contributors and registration. See the [DataCite Metadata Schema](https://schema.datacite.org/) for definitions of each metadata property.

The work record also includes information about relevant rights information, such as [Creative Commons](https://creativecommons.org/) licenses and [Local Contexts](doc:local-contexts-notices-and-labels)  Notices and the number of citations, views and downloads, when available.

### Actions

From the work record you can:

- **Add to ORCID Record**: On the left panel, the "Add to ORCID Record" button appears at the top. Click here to claim the DOI record and [link it to your ORCID profile](doc:orcid-claiming). 

> 📘 Connect DOIs to your ORCID profile
> 
> To manually link a DOI record to your ORCID profile, you should first log in with your ORCID credentials using the [sign-in button](doc:datacite-profiles-user-documentation) on the top right of the DataCite Commons page. Click on the "Add to ORCID Record" button that appears in the DOI record. Refer to the [documentation](doc:orcid-claiming) for more information.

- **Download Metadata**: Download the full metadata record in DataCite XML, DataCite JSON, schema.org, JSON LD or retrieve the citation in Citeproc JSON, Bibtex and RIS formats. Crossref DOIs with Open Access content available via the [Unpaywall](https://unpaywall.org/) API will display a link to the full text article.
- **"Cite as"**: Export the citation of the work; you can change the citation format using the dropdown selection.
- **Download Reports**: Download a CSV file containing a list of all Related Works. The list includes descriptions and formatted citations in APA style for up to 200 DOIs associated with the work.

### Views and Downloads

For works where the hosting repository has submitted usage reports to DataCite, monthly unique views and downloads are displayed in a graph over time.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/43d05f81bc40fff79f439a9981c8cc2cadaa0faea9b2193b3589a0aafc2dab7a-Screenshot_2026-03-25_at_16.49.39.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 📘 
> 
> Usage data can be submitted using the [Usage Reports API ](https://support.datacite.org/docs/views-and-downloads)or by implementing the [Usage Tracker](https://support.datacite.org/docs/datacite-usage-tracker) on DOI landing pages.

### Connections

#### Network Graph

This feature generates a force-directed graph that provides a high-level overview of the different types of works connected to the primary work DOI and the connections between them.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fba4e41d7952e7d5aa22fecdf31cd21bf3f9e4316f236114a22dd025aedd9bcb-Screenshot_2026-03-25_at_16.50.25.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


This visualization is based on the metadata of the primary work DOI and all works linked to it through metadata:

- Connections are captured via the [RelatedIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#) metadata of both the primary work DOI and the RelatedIdentifier metadata of the DOIs of the related works.
- All [relation types](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#b-relationtype) are captured, not just the [citation relation types](https://support.datacite.org/docs/contributing-citations-and-references).
- Works are grouped by resource type – based on the [resourceTypeGeneral](https://datacite-metadata-schema.readthedocs.io/en/4/properties/resourcetype/#a-resourcetypegeneral) metadata of each work DOI.

#### Related Works

Aggregated information about the Publication Year, Work Types and Licenses of the works related to the primary DOI are displayed in the Related Works section.

The options for filtering the list of related works:

- **Type to search...**: Filter the related works in the list using a keyword or advanced search.
- **Connection Types**: The radio buttons allow you to select the specific connection ([relationType](https://support.datacite.org/docs/contributing-citations-and-references)) the related work has to the primary work DOI.
- **Creators & Contributors**: Filter the related works list by a specific creator or contributor
- **Publication Year**: Filter the related works list by the publication year.
- **Work Type**: Filter the related works list by the work type (resourceTypeGeneral).
- **Registration Agency**: The DOI Registration Agency where the DOI was registered.
- **Repository**: The name of the Repository in DataCite.
- **Repository Type**: Corresponding to the [DataCite Repository Type](https://support.datacite.org/docs/update-repository-settings#type) where DataCite DOIs are stored.

> 📘 Citations
> 
> Create citations for your DOIs by including the RelatedIdentifier metadata following the guidelines outlined in the [citations and references documentation](https://support.datacite.org/docs/citations-and-references).

> 📘 DOI connections indexing
> 
> Depending on system load, DOI connections, like citations, references, and parts, may not appear immediately in Commons when DataCite DOI metadata is updated or created. If expected DOI connections do not appear 24 hours after a DOI is created or updated, please reach out to [support@datacite.org](mailto:support@datacite.org).

> 📘 Creators and contributors display
> 
> There is an upper limit of 20 creators or contributors that can be displayed in DataCite Commons for a DOI record. Some records have very large numbers of creators/contributors, so it is necessary to set a limit for display purposes. 
> 
> The full metadata record can be downloaded in JSON and XML or [retrieved via our API](ref:get_dois-id).