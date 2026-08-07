---
title: Registering DataCite DOIs for Awards
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
## Using DataCite DOIs for awards

This page provides general guidance on registering DataCite DOIs for awards, grants, and comparable entities. 

DataCite DOIs are suitable for a wide range of research outputs and resources, including awards and grants. 

Registering DOIs for awards and grants:

- Enables research funding organisations to keep track of awards and grants.
- Makes awards and grants easily citable by recipients.
- Facilitates tracking of outputs from funded activities through connected metadata.
- Supports landscape analysis for awards and grants

For more information on how DOIs and other persistent identifiers can be used by research funding organisations, see the [Guide for funders to support FAIR workflows & enable research tracking](https://doi.org/10.5281/zenodo.8289142).

## Metadata Recommendations

### Terminology

For the purpose of these recommendations, we define the following terms:

1. **Award:** An umbrella term for resources provided to individual(s) or organization(s) in support of research, academic output, or training, such as a specific instance of funding, grant, investment, sponsorship, scholarship, recognition, or non-monetary materials.
2. **Award scheme:** An umbrella term for a funding program, prize, or award category etc. - a framework for recognition and resource provision that support scholarly work, such as the ERC grants or the Nobel prizes.
3. **Award issuer**: The provider (organization) and manager (individuals) of the resources defined in an award scheme.
4. **Award DOI issuer:** The creator and publisher of the award DOI metadata.
5. **Award recipient**: A person or organization being awarded the resources defined in the award.
6. **Award project**: A planned set of work defined by a project plan or proposal that is selected to be funded by an award.

### Applying the DataCite Metadata Properties to Awards

[block:parameters]
{
  "data": {
    "h-0": "DataCite Property",
    "h-1": "Usage Notes for Grants",
    "h-2": "DataCite Cardinality",
    "h-3": "Required",
    "0-0": "1. Identifier",
    "0-1": " An identifier is a unique string that identifies a resource; here, the identifier is the DOI for the award.",
    "0-2": "1-n",
    "0-3": "Yes",
    "1-0": "2. Creator",
    "1-1": "Award issuer: The provider (organization) and manager (individuals) of the resources defined in an award scheme.",
    "1-2": "1-n",
    "1-3": "Yes",
    "2-0": "3. Title",
    "2-1": "The available and appropriate title(s) the award is known for. These could be:  \n  \n- The title of the specific award (following a naming convention decided by the award DOI issuer)\n- The title of the project funded by the award, specified in the title type field as AlternativeTitle.",
    "2-2": "1-n",
    "2-3": "Yes",
    "3-0": "4. Publisher",
    "3-1": "Award DOI issuer: The creator and publisher of the award DOI metadata.",
    "3-2": "1",
    "3-3": "Yes",
    "4-0": "5. Publication Year",
    "4-1": "The year in which the award was first issued.",
    "4-2": "1",
    "4-3": "Yes",
    "5-0": "7. Contributor",
    "5-1": "The recipient(s) of the award, which can be one or more people, teams, or organizations.",
    "5-2": "0-n",
    "5-3": "No",
    "6-0": "8. Date",
    "6-1": "Any relevant dates and time periods pertaining to the award, e.g.:  \n  \n- The period of time covered by the award. Enter two dates separated by a slash to indicate a date range (e.g. 2024-01-01/2024-12-31) and use dateType “Coverage”.\n- Extension period: Add an additional date property to indicate additional time period covered by an award extension. Enter two dates separated by a slash to indicate a date range, with dateType “Update”, and “Extension” in the dateInformation field.",
    "6-2": "0-n",
    "6-3": "No",
    "7-0": "10. Resource Type",
    "7-1": "Use resourceTypeGeneral [Award](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/resourceTypeGeneral/#award).  \n  \nUse the free text ResourceType value to specify the type of award.",
    "7-2": "1",
    "7-3": "Yes",
    "8-0": "11. Alternate Identifier",
    "8-1": "A local or internal award number may be included in AlternateIdentifier.",
    "8-2": "0-n",
    "8-3": "No",
    "9-0": "12. Related Identifier",
    "9-1": "Related identifiers of related research outputs and resources, including:  \n  \n- The identifier for related awards when there is a DOI.\n- Identifiers for outputs resulting from the award funding.\n- One or more project identifiers for projects funded by the award.\n- Identifiers for instruments used in the research funded by the award. See [Connecting Awards to Related Entities](doc:registering-datacite-dois-for-awards#connecting-awards-to-related-entities) table for specific relationType recommendations.",
    "9-2": "0-n",
    "9-3": "No",
    "10-0": "13. Size",
    "10-1": "Where applicable, include a quantity of resources provided by the award, including the numerical value + unit (e.g. EUR 10,000.00).  \n  \nSize can be used for monetary awards or other types of quantifiable resources, such as computing time.",
    "10-2": "0-n",
    "10-3": "No",
    "11-0": "17. Description",
    "11-1": "The description of the award. Depending on the award type, this may be a short summary used in the funding proposal or an outline of the funding purpose.",
    "11-2": "0-n",
    "11-3": "No",
    "12-0": "19. Funding Reference",
    "12-1": "When registering a DOI for a sub-award, use FundingReference to indicate the parent award and funding organization, including the awardTitle and awardNumber attributes where applicable.  \n  \nIf the parent award has an identifier, we recommend both including this the awardNumber attribute for the FundingReference and adding a RelatedIdentifier. See  [Connecting Awards to Related Entities](doc:registering-datacite-dois-for-awards#connecting-awards-to-related-entities) table for specific relationType recommendations.",
    "12-2": "0-n",
    "12-3": "No",
    "13-0": "20. Related Item",
    "13-1": "The award scheme (for example, a named funding program/category) through which the award is issued. The RelatedItem sub-properties can be applied as follows:  \n  \n- Indicate that the award is issued through the award scheme with the relationType “IsPartOf”.\n- Include the name of the award scheme in the Title sub-property.\n- Include the award issuer (responsible for administering the award scheme) in the Creator sub-property.\n- Where available, include an identifier for the award scheme in relatedItemIdentifier and add a corresponding RelatedIdentifier property. For more information, refer to the general guidance on [Using RelatedItem for publication information and related resources](https://datacite-metadata-schema.readthedocs.io/en/4.5/guidance/related-item-guide/).",
    "13-2": "0-n",
    "13-3": "No"
  },
  "cols": 4,
  "rows": 14,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


There may be additional fields of interest depending on the nature of the award, such as “geoLocation” for facility based awards, “subject” for grants designed to support work in specific disciplinary domains.

## Connecting Awards to Related Entities

The DataCite Metadata Schema can be used to connect awards to related entities—including works, people, and organizations. This table shows several connections that can be specified:

[block:parameters]
{
  "data": {
    "h-0": "Connection",
    "h-1": "DataCite Metadata Property",
    "h-2": "Connecting Sub-property",
    "h-3": "Recommended PID",
    "h-4": "Notes",
    "0-0": "Award → award manager",
    "0-1": "Creator",
    "0-2": "Creator - nameIdentifier",
    "0-3": "ORCID iD for person  \n  \nROR ID for organization",
    "0-4": "",
    "1-0": "Award → recipients",
    "1-1": "Contributor",
    "1-2": "Contributor - nameIdentifier",
    "1-3": "ORCID iD for person  \n  \nROR ID for organization",
    "1-4": "",
    "2-0": "Award → award DOI issuer",
    "2-1": "Creator",
    "2-2": "Creator - nameIdentifier",
    "2-3": "ROR ID for organization",
    "2-4": "",
    "3-0": "Award → award DOI issuer",
    "3-1": "Publisher",
    "3-2": "Publisher - PublisherIdentifier",
    "3-3": "ROR ID for organization",
    "3-4": "",
    "4-0": "Recipients → affiliations",
    "4-1": "Contributor - affiliation",
    "4-2": "Contributor - affiliation - affiliationIdentifier",
    "4-3": "ROR ID for organization",
    "4-4": "",
    "5-0": "Award → award scheme",
    "5-1": "RelatedIdentifier with relationType: IsPartOf",
    "5-2": "-",
    "5-3": "DOI",
    "5-4": "",
    "6-0": "Award → project",
    "6-1": "RelatedIdentifier  \n  \n- When award and project have a 1-1 correspondence: relationType Requires\n\n- When the award is one component of a larger project: relationType IsPartOf",
    "6-2": "-",
    "6-3": "DOI",
    "6-4": "",
    "7-0": "Award → output",
    "7-1": "RelatedIdentifier with relationType: References",
    "7-2": "-",
    "7-3": "DOI",
    "7-4": "Ideally, the connection should be established by the recipient by acknowledging the award when sharing outputs (enter award DOI in the FundingReference property of each related output DOI).",
    "8-0": "Award → data management plan (DMP)",
    "8-1": "RelatedIdentifier:  \n  \n- When DMP is required as part of the application: relationType Requires\n\n- When DMP is a planned output shared after grant award: relationType IsSupplementedBy",
    "8-2": "-",
    "8-3": "DOI/DMP-ID",
    "8-4": "",
    "9-0": "Award → other resources",
    "9-1": "RelatedIdentifier  \n  \n- For an instrument or facility: relationType: Requires",
    "9-2": "-",
    "9-3": "DOI",
    "9-4": "When the award is not monetary, but an allocation of resource i.e. usage of instruments or facilities, the issuance of the award “requires” the instrument or facility.",
    "10-0": "Award → other award",
    "10-1": "RelatedIdentifier  \n  \n- For parent-award/sub-awards: relationType IsPartOf/HasPart\n\n- For follow-up or extension awards: relationType Continues/IsContinuedBy\n\n- For other related awards, without a hierarchical or sequential relationship:  relationType References",
    "10-2": "-",
    "10-3": "DOI",
    "10-4": ""
  },
  "cols": 5,
  "rows": 11,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]