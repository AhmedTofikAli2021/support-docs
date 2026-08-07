---
title: RelationType for Citations and References
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
Following the Scholix framework, in order to create a link between a dataset and an article, there are  3 metadata fields that must be populated: relatedIdentifier, relatedIdentifierType and relationType (see previous section).  This section looks in more detail at the use of relationType, how/when these relations become citations and how this information will be exposed for data level metrics. 

The [DataCite Metadata Schema](https://schema.datacite.org/) defines relationType as a "Description of the relationship of the resource being registered (A) and the related resource (B)" 

The full list of relationType controlled vocabulary and directionality is shown below. A definition of each relationType is included in the PDF on the [DataCite Metadata Schema website](https://schema.datacite.org/).

[block:parameters]
{
  "data": {
    "0-0": "IsCitedBy\t\t       \nIsSupplementTo \t\nIsContinuedBy \t  \nIsDescribedBy \t   \nHasMetadata \t     \nHasVersion \t \t    \nIsNewVersionOf \t \nIsPartOf \t\t\t      \nIsReferencedBy   \nIsDocumentedBy \t \nIsCompiledBy \t   \nIsVariantFormOf \t\nIsIdenticalTo \t\t\t\nIsReviewedBy \t \nIsDerivedFrom \nRequires \nIsObsoletedBy",
    "0-1": "Cites \nIsSupplementedBy \nContinues \nDescribes \nIsMetadataFor\nIsVersionOf \nPreviousVersionOf\nHasPart \nReferences \nDocuments\nCompiles \nIsOriginalFormOf \n*\nReviews \nIsSourceOf \nIsRequiredBy \nObsoletes"
  },
  "cols": 2,
  "rows": 1
}
[/block]
A relationType should be selected to best describe the relation and direction between the subject and the object. This information will be then be used to define whether the link is a **Citation**, a **Reference** or another type of **Relation**. 

The figure below explains how each relationType will be counted by DataCite for Data Level Metrics:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a1dbaa9-relationType.png",
        "relationType.png",
        3618,
        1487,
        "#9a9896"
      ]
    }
  ]
}
[/block]
## Use Case

Dataset A is cited in Article B. The repository is updating the DOI metadata for dataset A and have already included the relatedIdentifier and relatedIdentifierType of Article B. They need to select the relationType.

1. Describe the relation
Following the recommendation above, the repository must choose the most appropriate of these 3 relationTypes: **IsCitedBy / IsReferencedBy / IsSupplementTo**.  The relationType can now be included in the DOI metadata of dataset A. This will count as 1 citation for dataset A.
[block:callout]
{
  "type": "info",
  "body": "Only one relationType should be used to describe a link between a dataset and an article. It is not necessary to select more than one, even if multiple relationTypes could apply."
}
[/block]
2. Select the direction
Keep in mind the direction of the relationType. In this case dataset A (the subject) IsReferencedBy/IsCitedBy/IsSupplementTo Article B (the object).

3. Data level metrics
This information can now be exposed via [Event Data](doc:eventdata-guide) in [DataCite Search](doc:datacite-search-user-documentation) and via the [Data Metrics Badge](doc:displaying-usage-and-citations-in-your-repository).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dee9c59-citations.png",
        "citations.png",
        2635,
        1662,
        "#e6e8e9"
      ]
    }
  ]
}
[/block]