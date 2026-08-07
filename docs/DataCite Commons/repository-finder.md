---
title: Repository Search in DataCite Commons
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
The Repository Search in [DataCite Commons](https://commons.datacite.org/) is designed so researchers, repository managers, and the wider community can search for repositories and retrieve repository metadata, metrics and link out to see works related to the repository. Researchers can use this service to assess whether to use the repository to deposit their content. Below is information about how to search for a repository, filter the results, and then view the individual repository page.

> 👍 Make sure you link your Fabrica Repository account to the re3data profile
> 
> To ensure your Repository in Fabrica is linked to the corresponding re3data record, make sure you add the [re3data Record](doc:update-repository-settings#re3data-record) metadata in the [Repository settings in Fabrica](doc:fabrica-update-repository#re3data-record).
> 
> 
> 
> ![](https://files.readme.io/2bdb6c2-Screenshot_2023-02-01_at_15.22.17.png "Screenshot 2023-02-01 at 15.22.17.png")

## Search

The Repository Search feature in DataCite Commons enables searching for any repository profile that exists in DataCite and [re3data](https://www.re3data.org/). 

> 📘 
> 
> DataCite Commons uses [GraphQL](doc:datacite-graphql-api-guide) queries (not the [REST API](doc:api)) to search both Fabrica and re3data. REST API queries will only search Fabrica, so it's normal to see differences between the results retrieved in Commons and the REST API.

Navigate to the **Repositories** tab and enter a repository name or keywords in the search box:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/190b9da-commons_repository_searchbar.png",
        "Screenshot 2022-02-23 at 12.38.18.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

If there are matches in re3data and/or Fabrica a list of repository matches are returned:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/efb7180-commons_repository_searchresults.png",
        "Screenshot 2022-02-23 at 12.32.01.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

## Filter

Use the check boxes in the panel of the left to filter the results based on the following criteria:

### Criterias Compliance

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c01fe84-commons_repository_criterias.png",
        "Screenshot 2022-02-23 at 14.51.49.png",
        ""
      ],
      "align": "center",
      "sizing": "300px"
    }
  ]
}
[/block]

**Enabling FAIR Data Project**

Repositories in **re3data** that meet the criteria of the Enabling FAIR Data Project: 

- The repository is a domain repository for the Earth, space and environmental sciences (the repository has special expertise and is used by the community).
- The repository provides open access to its data (research data hosted by the repository are accessible without restrictions).
- The repository uses persistent identifiers (persistent identifiers such as DOIs uniquely identify datasets, enable the linking to publications, and help with discovery).

**[FAIRsFAIRs project](https://www.fairsfair.eu/)**

Repositories in **re3data** that meet the criteria of the FAIRsFAIR Project: 

- The repository provides open access to its data (research data hosted by the repository are accessible without restrictions).
- The repository uses persistent identifiers (persistent identifiers such as DOIs uniquely identifier datasets, enable the linking to publications, and help with discovery).
- The repository is certified e.g., the CoreTrustSeal.

### Certificates

Filter by any available [certificate](https://www.rd-alliance.org/groups/rdawds-certification-digital-repositories-ig.html) .

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/808458e-commons_repository_certificates.png",
        "Screenshot 2022-06-09 at 15.52.25.png",
        ""
      ],
      "align": "center",
      "sizing": "300px"
    }
  ]
}
[/block]

### Software

Filter by the type of software used by the repository.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65efb99-commons_repository_software.png",
        "Screenshot 2022-06-09 at 15.51.31.png",
        ""
      ],
      "align": "center",
      "sizing": "300px"
    }
  ]
}
[/block]

# Repository Page

Click on the name name of the repository to open the individual Repository page in DataCite Commons. The Repository dashboard displays the metadata available in the Fabrica record and/or re3data. 

## Dashboard

The repository record summarises metrics of the works related to the repository:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6622b74-commons_repository_stats.png",
        "Screenshot 2022-03-11 at 17.35.29.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

- Works  
  The total number of DOIs related to the repository.

- Citations  
  The total [number of Citations](doc:citations-and-references) for all of the repository’s related works.

- Views  
  The total [number of Views](doc:views-and-downloads) related to the repository’s related works.

- Downloads  
  The total [number of Downloads](doc:views-and-downloads) related to the repository’s related works.

The record also shows metadata associated with the repository from re3data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/176add7-commons_repository_overview.png",
        "Screenshot 2022-02-23 at 14.56.56.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

The panel of the left of the page includes the following links and buttons:

**Go to Repository**  
Redirects to the URL of the repository

**Find Related Works **  
Redirects to a list of DOIs registered by the repository.

**Contacts**  
If there is a email in the re3data profile of the repository, it will appear in the DataCite Commons record. Clicking on the link redirects to a mailto link with the email address.

## Deposits

The charts at the bottom of the Repository record display information sourced from the [DataCite metadata](http://schema.datacite.org/) of the DOIs registered by the Repository:

- Publication Year  
  Aggregate of the publicationYear (property 5) from DataCite DOI metadata.

- Work Types  
  Aggregate of the resourceTypeGeneral (property 10.a) from DataCite DOI metadata.

- Licenses  
  Aggregate of the Rights (property 16) from DataCite DOI metadata.

- Top Depositors  
  Aggregate of nameIdentifier = ORCID (property 2.4) in the Creator property from DataCite DOI metadata.

- Fields of Science  
  Aggregate of Subject metadata (property 6) from DataCite DOI metadata, only where the OECD Fields of Science controlled vocabulary is used.

- Work Languages  
  Aggregate of the Language (property 9) from DataCite DOI metadata.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0fcd4a9-commons_repository_charts.png",
        "Screenshot 2022-03-11 at 16.57.29.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

The Repository dashboard also includes an advisory message at the bottom with more information about the repository and general information about research data management.

![](https://files.readme.io/42e7f19-Screenshot_2022-03-11_at_17.25.17.png "Screenshot 2022-03-11 at 17.25.17.png")

## FAQ

**Why would I use Repository Search in DataCite Commons?**  
Repository Search was designed to make it easy for researchers to find repositories that accept deposit of research data. As a secondary goal, we hope the tool can help to promote good practices related to research data and serve as a reference for listing funder, publisher, and other repository recommendations.

**What is re3data?**  
[re3data](https://www.re3data.org/) is a registry that provides a searchable and machine-actionable metadata about research data repositories. The Repository Search tool provides a front-end to re3data to simplify the interface for researchers to use to find an appropriate data repositories to deposit their data. The results from Repository Search are linked to more detailed information and additional functionality that are also available in the native re3data interface.

**What does FAIR mean?**  
The [FAIR Data Principles](https://www.nature.com/articles/sdata201618) are a set of guiding principles in order to make data findable, accessible, interoperable and reusable (Wilkinson et al., 2016). The design and development of the tool was directly informed by the work of targeted adoption groups (TAGs) within the Enabling FAIR project and its resulting [commitment](http://www.copdess.org/enabling-fair-data-project/commitment-to-enabling-fair-data-in-the-earth-space-and-environmental-sciences/) statement.

**What criteria are used in determining relevance and order of results when searching by keyword?**  
The order of results is determined by the re3data search index. Search terms found in the repository name, subject area and keywords fields have higher relevance, to lesser extend also search terms found in the repository description.

**What criteria are used to include repositories in the Enabling FAIR for Earth and Space Sciences Community list?**  
The Enabling FAIR project brought together over 300 stakeholders in the earth and space sciences in a series of workshops and targeted adoption groups (TAGs) that included researchers, publishers, funders, repositories and data facilities, librarians, professional associations, and others in the research community. Their initial list of criteria include data repositories in the earth and space sciences domain that support open access, provide persistent identifiers, and accept data for deposit. Data repositories that have gone through a process to be certified as trustworthy, such as the Core Trust Seal, are highlighted. In the future, we hope to add additional lists of recommendations as they become available and are suggested.

**Why are there fewer repositories in Repository Search in DataCite Commons compared to the re3data website?**  
Repository Search only shows the repositories from [re3data](https://www.re3data.org) that allow data uploads (properties open or restricted).

**A repository that I expected to see isn't listed in the results. What can I do?**  
Repository Search queries and provides results from re3data. New repositories and changes to repositories in re3data can be [suggested](https://www.re3data.org/suggest) and incorporated to improve listing and relevance. If you are a repository manager, these guidelines are a good place to start.