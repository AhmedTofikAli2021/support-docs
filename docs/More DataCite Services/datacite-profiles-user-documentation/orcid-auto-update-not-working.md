---
title: ORCID Auto-Update Troubleshooting Guide
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
For information about how to enable the ORCID auto-update see our [guide on how to activate the ORCID auto-update](doc:datacite-and-orcid#2-orcid-auto-update).

If everything is set up correctly, but the auto-update is not working as expected, then there are a few things you can check.

## The date the auto-update enabled

Auto-update will only trigger for findable DOIs registered or updated **after** the user enables the auto-update token. To trigger the ORCID auto-update for existing DOIs (registered before the token was enabled), you will need to make an update to one of the following metadata fields:

- Creator
- RelatedIdentifier
- FundingReference

## Invalid token

Some claims may not work if permission has been revoked in your ORCID settings and the token that DataCite has is no longer valid. To fix this you can:

1. Check the third party permission settings in your ORCID record. 
2. Log into [DataCite Profiles](https://profiles.datacite.org/) to delete the token and then authorise a new one.

## Contributor

The ORCID auto update claiming only works if your ORCID iD is included in the "creators" field in the DOI metadata. If your ORCID iD is only included in the "contributor" metadata field of the DOI then this won't be picked up by the ORCID auto-update. In DataCite the contributor has a much broader meaning than author/creator. If users claim works as a "contributor" it may appear that they actually authored the work.

## IsVersionOf

If the DOI record contains any of the following relationType in the metadata it will not be picked up by the ORCID auto-update.

```text
[“IsIdenticalTo”, “IsPartOf”, “IsPreviousVersionOf”, “IsVersionOf”]
```

This is because some repositories, for example Figshare and Zenodo, generate lots of versions of a DOI. DataCite only pushes the original DOI to the ORCID record, and does not push multiple versions with a relationshipType mentioned above.

If none of the above helps please contact DataCite support [support@datacite.org](mailto:support@datacite.org)