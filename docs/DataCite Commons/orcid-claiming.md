---
title: Add a DOI to Your ORCID Record
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
The "Add to ORCID Record" feature in [DataCite Commons](https://commons.datacite.org/) allows a researcher to manually claim a DOI of their work and link it to their [ORCID record](https://orcid.org/).

> 📘 DataCite Profiles
> 
> You need a [DataCite Profiles](https://profiles.datacite.org/) account to use this service. In order for ORCID claiming to work, an ORCID token must be enabled. Follow the instructions in the [Profiles documentation](doc:datacite-profiles-user-documentation).
> 
> Only DataCite DOIs can be claimed in DataCite Commons.

To claim a DOI in DataCite Commons, first ** sign in ** by clicking the button at the top right of the page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a84aa90-Screen_Shot_2023-06-13_at_1.39.33_PM.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]

1. Search for a DOI using the search box. Click to open the full record of the DOI. Click on the **"Add to ORCID Record"** button in the sidebar.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe261c5-Screen_Shot_2023-06-13_at_1.44.35_PM.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "300px",
      "border": true
    }
  ]
}
[/block]

2. The **"Claim waiting"** message will appear. Claiming may take a few seconds to complete. If the error "No user and/or ORCID token" appears, check that the ORCID token is enabled in [DataCite Profiles](doc:datacite-profiles-user-documentation).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/51c0321-Screen_Shot_2023-06-13_at_1.47.16_PM.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "300px",
      "border": true
    }
  ]
}
[/block]

Once complete, the DOI will appear in the associated ORCID record and the button will change to **"Remove Claim"**. Clicking "Remove Claim" will remove the DOI from the ORCID record if the claim was made in error.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a345a4d-Screen_Shot_2023-06-13_at_1.47.43_PM.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "300px",
      "border": true
    }
  ]
}
[/block]

> 🚧 Researcher Profiles
> 
> Claims are sent to ORCID and appear in your ORCID profile. They do not appear in the [DataCite Researcher Profile](doc:datacite-researcher-profiles). Only DOIs that have the ORCID iD included in the DOI metadata are linked to the DataCite Researcher Profile.

> 📘 Why is it different from the ORCID auto update?
> 
> Claiming a DOI in [DataCite Commons](https://commons.datacite.org/) is useful when you want to claim a work that does not include your ORCID iD in the DOI metadata. You can also automatically add DOIs to your ORCID account that include your ORCID iD in the creator metadata using [ORCID Auto-Update](doc:how-to-activate-orcid-auto-update).