---
title: DataCite and ORCID
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
DataCite provides Persistent Identifiers (DOIs) for all research outputs. ORCID provides Persistent Identifiers (ORCID iDs) for all researchers. The two organisations work closely together to identify research and connect it to the researchers that created it.

DataCite's integration with ORCID's API means it is quick and easy for researchers to link any works which have a DataCite DOI to their ORCID profile. 

Here we describe the two ways in which your works with a DataCite DOI can be linked to your ORCID profile.

> 📘 What is a claim?
> 
> In DataCite, when a work (a DOI) is sent to an ORCID record via either of the methods outlined below, this is known as a “claim” and simply means a request has been sent to ORCID to connect a specific DOI to an ORCID profile. Failed claims will also be listed in the settings of your [Profiles](doc:datacite-profiles-user-documentation) account.

# 1. ORCID Search & Link Wizard

The [ORCID Search & Link wizard](https://info.orcid.org/documentation/workflows/search-and-link-workflow/) allows you to manually add your works to your ORCID record from [DataCite Commons](https://support.datacite.org/docs/datacite-commons).

Start by logging in to your ORCID account and then scroll down to the "Works" section. Click the “Add” button and a drop down list of options will appear. Select Search & Link and then scroll down to select “DataCite”.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55dc263-Screenshot_2023-08-24_at_14.35.54.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ec6c44-Screenshot_2023-08-24_at_14.36.27.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


If you have already created a [DataCite Profiles account](doc:datacite-profiles-user-documentation), you will arrive on the Settings page (otherwise you will be prompted to create a Profiles account). From here, click the drop down at the top right and navigate to [DataCite Commons](https://commons.datacite.org/) where you can search for your works by entering your name or ORCID iD:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/568be9e-Screenshot_2023-08-31_at_13.58.41.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


Click on the DOI record in DataCite Commons and use the "Add to ORCID Record" button in the DOI record:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa5bd6a-Screenshot_2023-08-31_at_14.48.08.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 👍 ORCID
> 
> You can find detailed instructions in the DataCite Commons documentation [Add a DOI to Your ORCID](doc:orcid-claiming).

# 2. ORCID Auto-Update

Enabling the [ORCID](https://orcid.org/) auto-update means DataCite will automatically update your ORCID record every time a new DOI is registered with your ORCID iD in the metadata.

> 📘 Requirements for ORCID auto-update
> 
> For the auto-update to work you will need:
> 
> - An ORCID record.
> - A [DataCite Profiles](doc:datacite-profiles-user-documentation) account with ORCID permissions enabled.
> - The DOI metadata includes your ORCID iD.

To automatically send claims from DataCite to your ORCID record, you need to obtain permissions from ORCID in the form of a token. In the Settings page of  the [DataCite Profiles Service](https://profiles.datacite.org/) enable the ORCID auto-update by clicking "Get ORCID Token". Please see a detailed description on our [DataCite Profile pages](doc:datacite-profiles-user-documentation).

After you have enabled the ORCID auto-update in the Profile Service, you will be prompted in your ORCID profile to allow DataCite to automatically add works to your ORCID record. Your approval here will finalize your registration for auto-update. You can revoke your permission for this auto-update at any time in the settings of your ORCID profile.

> 👍 
> 
> Auto-update will trigger for findable DOIs registered or updated after the user enables the auto-update. To trigger the ORCID auto-update for existing DOIs, you will need to make an update to one of the following fields:
> 
> - Creator
> - RelatedIdentifier
> - FundingReference

### Troubleshooting

If you have any issues with the auto-update functionality please check out the [ORCID auto-update troubleshooting guide](doc:orcid-auto-update-not-working) or get in contact by sending an email to [support@datacite.org](mailto:support@datacite.org).