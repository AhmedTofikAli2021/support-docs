---
title: Where does the license information come from in DataCite Commons?
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
In [DataCite Commons](https://commons.datacite.org/) you will notice that each of the different profiles for [Works](doc:works-in-datacite-commons), [People](doc:people-in-datacite-commons), [Organizations ](doc:organizations-in-datacite-commons)and [Repositories](doc:repository-finder) include information at the bottom about the Related Works (DOIs). This information is generated based on the connections established in the DOI metadata.

The Licenses graph that appears in the Related Works section pulls information from the [rightsIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4.6/properties/rights/#b-rightsidentifier) (16.b) property. This is used to generate the graph and the number of license types is displayed as a percentage of the total DOIs in the Related Works.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fccca5a17ce8dff9abab343a5af51ea07c41f755566a73a4a8173e5f4c44a380-Screenshot_2025-04-28_at_14.48.50.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]




If no license information is included in the rightsIdentifier property when a DOI is registered, the Licenses graph will automatically represent this as “unknown.” You can correct this by updating your DOI rightsList metadata to include the rightsIdentifier property.

More information and definitions of all the properties can be found in the [DataCite Metadata Schema](https://schema.datacite.org/).