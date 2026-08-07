---
title: >-
  The Form in Fabrica only accepts a limited number of nested metadata
  properties, how can I input more?
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
The [Form](doc:create-a-doi-via-form) in DataCite Fabrica allows users to input all of the available metadata properties in the [DataCite Metadata Schema](http://schema.datacite.org/). However, the Form does limit the number of times certain metadata fields can be repeated. These limitations prevent the interface from becoming very large and unmanageable.

There are two solutions for inputting large numbers of nested metadata properties: using either the [File Upload](doc:fabrica-create-doi-file-upload) in Fabrica or the [API](doc:api). Below is an example of the “subject” metadata repeated in XML:
[block:code]
{
  "codes": [
    {
      "code": "   <subjects>\n        <subject>Lepidocolaptes angustirostris</subject>\n        <subject>Elaenia cristata</subject>\n        <subject>Ammodramus humeralis</subject>\n        <subject>Neothraupis fasciata</subject>\n        <subject>GBS</subject>\n        <subject>MaxEnt</subject>\n        <subject>FOS: Biological sciences</subject>\n    </subjects>",
      "language": "text"
    }
  ]
}
[/block]


example from Dryad: https://doi.org/10.5061/dryad.w9ghx3frh