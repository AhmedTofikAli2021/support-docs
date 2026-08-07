---
title: Create a DMP ID
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
A DMP ID is a DOI with the resourceTypeGeneral “OutputManagementPlan”. Since the release of schema 4.4 the resourceTypeGeneral controlled vocabulary now includes this option. A DMP ID is created in the same way as a normal DOI, with the same required fields, but must include the “OutputsManagementPlan” resourceTypeGeneral to be recognised. In addition, the **Contributors should always be included in the metadata**.

EXAMPLES:

Fabrica

![](https://files.readme.io/d0750ba-Screen_Shot_2021-03-31_at_09.50.16.png "Screen Shot 2021-03-31 at 09.50.16.png")

XML 

```text
<resourceType resourceTypeGeneral="OutputManagementPlan"/>
```

JSON

```Text json
"resourceTypeGeneral": "OutputManagementPlan"
```