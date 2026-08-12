---
title: Accessibility Achievements
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/works-in-datacite-commons
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Accessibility Achievements in DataCite Commons provide information about the openness of a researcher’s works based on the license information in the DOI metadata. The Accessibility Achievements appear in the [researcher profile in DataCite Commons](https://commons.datacite.org/orcid.org/0000-0002-9647-4045). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0bc889f-Screen_Shot_2021-07-29_at_15.10.51.png",
        "Screen Shot 2021-07-29 at 15.10.51.png",
        2102,
        362,
        "#f5f6f6"
      ]
    }
  ]
}
[/block]
The DOIs are linked to the profiles based on the [ORCID](https://orcid.org/) of the researcher. 

Each achievement has a badge. The badges are allocated based on the information held in the metadata shared by the repository where the researcher's content is deposited. The license information is contained in property 16 "rights" of the [DataCite Metadata Schema](http://schema.datacite.org/):
[block:code]
{
  "codes": [
    {
      "code": "<rightsList>\n    <rights xml:lang=\"en-US\" schemeURI=\"https://spdx.org/licenses/\" rightsIdentifierScheme=\"SPDX\" rightsIdentifier=\"CC0 1.0\" rightsURI=\"https://creativecommons.org/publicdomain/zero/1.0/\" />\n  </rightsList>",
      "language": "xml"
    }
  ]
}
[/block]

There are four badges that can be awarded:


## Open Hero Badge 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9ea7d5-Screen_Shot_2021-07-29_at_14.26.12.png",
        "Screen Shot 2021-07-29 at 14.26.12.png",
        230,
        298,
        "#9f9f9f"
      ]
    }
  ]
}
[/block]
*n% of the researcher's associated DOIs have metadata with rights as CC-BY, CC0, or public domain license.*
[block:callout]
{
  "type": "info",
  "body": "At least one of the researcher's associated DOIs have metadata with rights CC-BY-*, CC0, or public domain license and the percentage of their DOIs with these licenses. See [(full list of licenses)](doc:open-badge#full-list-of-licenses)."
}
[/block]
## Open License Badge 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/73e4f01-Screen_Shot_2021-07-29_at_14.26.28.png",
        "Screen Shot 2021-07-29 at 14.26.28.png",
        244,
        326,
        "#9a9a9a"
      ]
    }
  ]
}
[/block]
*Every single one of your publications is free to access online. Open access helps real people, and that's pretty heroic.*
[block:callout]
{
  "type": "info",
  "body": "Every single one of the researcher’s associated DOIs have metadata with rights CC-BY-*, CC0, or public domain license [(full list of licenses)](doc:open-badge#full-list-of-licenses)."
}
[/block]
##  Open Access Badge 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/59e3fc5-Screen_Shot_2021-07-29_at_14.26.36.png",
        "Screen Shot 2021-07-29 at 14.26.36.png",
        250,
        288,
        "#dfdfdf"
      ]
    }
  ]
}
[/block]
*n% of your research is free to read online.*
[block:callout]
{
  "type": "info",
  "body": "At least one of the researcher's associated DOIs have metadata with contentUrl. This is sent via the DataCite [REST API](doc:api)"
}
[/block]
## Open Science Triathlete Badge 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8d3cc96-Screen_Shot_2021-07-29_at_14.26.45.png",
        "Screen Shot 2021-07-29 at 14.26.45.png",
        286,
        280,
        "#dfdfdf"
      ]
    }
  ]
}
[/block]
*Congratulations, you hit the trifecta. You have an Open Access paper, open dataset, and open source software.*
[block:callout]
{
  "type": "info",
  "body": "All of the researcher's associated DOIs have metadata with rights information that has at least; One Open Access paper (text or JournalArticle), one open dataset (dataset), and one open source software (software)."
}
[/block]
## Full list of licenses: 
[block:parameters]
{
  "data": {
    "0-0": "[Creative Commons Attribution 1.0 Generic](https://spdx.org/licenses/CC-BY-1.0.html)",
    "1-0": "[Creative Commons Attribution 2.0 Generic](https://spdx.org/licenses/CC-BY-2.0.html)",
    "2-0": "[Creative Commons Attribution 2.5 Generic](https://spdx.org/licenses/CC-BY-2.5.html)",
    "3-0": "[Creative Commons Attribution 3.0 Unported](https://spdx.org/licenses/CC-BY-3.0.html)",
    "4-0": "[Creative Commons Attribution 3.0 Austria](https://spdx.org/licenses/CC-BY-3.0-AT.html)",
    "5-0": "[Creative Commons Attribution 3.0 United States](https://spdx.org/licenses/CC-BY-3.0-US.html)",
    "6-0": "[Creative Commons Attribution 4.0 International](https://spdx.org/licenses/CC-BY-4.0.html)",
    "7-0": "[Creative Commons Public Domain Dedication and Certification](https://spdx.org/licenses/CC-PDDC.html)",
    "8-0": "[Creative Commons Zero v1.0 Universal](https://spdx.org/licenses/CC0-1.0.html)",
    "9-0": "[Public Domain Mark 1.0](https://creativecommons.org/publicdomain/mark/1.0/)",
    "0-1": "CC-BY-1.0",
    "1-1": "CC-BY-2.0",
    "2-1": "CC-BY-2.5",
    "3-1": "CC-BY-3.0",
    "4-1": "CC-BY-3.0-AT",
    "5-1": "CC-BY-3.0-US",
    "6-1": "CC-BY-4.0",
    "7-1": "CC-PDDC",
    "8-1": "CC0-1.0",
    "9-1": "CC-PDM-1.0"
  },
  "cols": 2,
  "rows": 10
}
[/block]
To see how the results are generated query the [Graph QL API](doc:datacite-graphql-api-guide) for all DOIs with a certain license:
[block:code]
{
  "codes": [
    {
      "code": "```graphql\n{\n  person(id: \"https://orcid.org/0000-0001-9623-2225\") {\n    name\n    works {\n      totalCount\n\t\t\ttotalContentUrl\n      totalOpenLicenses\n      openLicenseResourceTypes{\n        id\n        count\n      }\n    }\n  }\n}\n\n\n```",
      "language": "json"
    }
  ]
}
[/block]