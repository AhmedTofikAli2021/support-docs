---
title: Repositories in DataCite Commons
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
Use the Repositories tab to search for any Repository belonging to a DataCite Member.

Navigate to the **Repositories** tab and enter a repository name or keywords in the search box.

## Filter

Use the check boxes in the panel of the left to filter the results based on the following criteria:

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

Click on the name name of the repository to open the individual Repository page in DataCite Commons. 

## Dashboard

The repository record summarises metrics of the works in the repository:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4340ec9d3e93a508cecdb73477b2827a684d8d3af3f701231c52df7f584c296c-Screenshot_2025-10-30_at_16.48.57.png",
        "Screenshot 2022-03-11 at 17.35.29.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


- Works  
  The total number of DOIs in the repository.

- Citations  
  The total [number of Citations](doc:citations-and-references) for all of the repository.

- Views  
  The total [number of Views](doc:views-and-downloads) of the repository’s works.

- Downloads  
  The total [number of Downloads](doc:views-and-downloads) of the repository’s works.

## Related Works

The charts at the bottom of the Repository record display information sourced from the [DataCite metadata](http://schema.datacite.org/) of the DOIs registered by the Repository:

- Publication Year  
  Aggregate of the publicationYear (property 5) from DataCite DOI metadata.

- Work Types  
  Aggregate of the resourceTypeGeneral (property 10.a) from DataCite DOI metadata.

- Licenses  
  Aggregate of the rightsIdentifier (property 16.b) from DataCite DOI metadata.

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
        "https://files.readme.io/46797704ceae517cdd8e1983bc0a9ccf78a3aadfec067dc14db9a1f7fb7987fb-Screenshot_2025-10-30_at_16.49.51.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]