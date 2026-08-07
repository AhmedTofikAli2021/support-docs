---
title: >-
  How can I represent resources that have been translated into different
  languages using the DataCite Metadata Schema?
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
When a resource is translated into another language(s), you can assign a DOI to each different language version. The latest version of the [DataCite Metadata Schema](https://schema.datacite.org/) includes the new [relationType](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/) pair: [HasTranslation](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/#hastranslation) and[ IsTranslationOf](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/#istranslationof). This means you can connect the different translations via the DOI metadata:

–[ IsTranslationOf](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/#istranslationof): When a resource is shared in one language, then later translated to another, use “IsTranslationOf” to link the translation to the original.  
Definition: Indicates A (the resource you are sharing) has a translation B

<relatedIdentifier relatedIdentifierType="DOI" relationType="IsTranslationOf">10.21384/828a-cm38</relatedIdentifier>

 – [HasTranslation](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/#hastranslation): When a resource is shared in one language, then later translated to another, use “HasTranslation” to link the original resource to its translation.  
Definition: Indicates A (the resource you are sharing) is a translation of B 

<relatedIdentifier relatedIdentifierType="DOI" relationType="HasTranslation">10.21384/g01j-jm06</relatedIdentifier>

Schema version 4.6 also includes the [contributorType: Translator](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/contributorType/#translator). This is a person, organization, or automated system responsible for converting the content of a resource from one language into another, preserving its meaning and intended message. This contributorType should be applied to DOI metadata for a resource that has been translated from another resource.

[Live example of the contributorType: Translator in JSON format](https://api.datacite.org/application/vnd.datacite.datacite+json/10.5438/s7c0-y897)