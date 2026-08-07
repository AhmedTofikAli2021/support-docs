---
title: >-
  The Form in Fabrica only accepts a limited number of nested metadata
  properties. How can I input more?
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
The [DOI Form](doc:fabrica-doi-form) in DataCite Fabrica allows users to input all of the available metadata properties in the [DataCite Metadata Schema](http://schema.datacite.org/). However, the Form does limit the number of times certain metadata fields can be repeated. These limitations prevent the interface from becoming very large and unmanageable.

There are two solutions for inputting large numbers of nested metadata properties: using either the [File Upload](doc:fabrica-doi-file-upload) in Fabrica or the [API](doc:api). Below is an example of the “subject” metadata repeated in XML:

```xml
<subjects>
        <subject>Lepidocolaptes angustirostris</subject>
        <subject>Elaenia cristata</subject>
        <subject>Ammodramus humeralis</subject>
        <subject>Neothraupis fasciata</subject>
        <subject>GBS</subject>
        <subject>MaxEnt</subject>
        <subject>FOS: Biological sciences</subject>
</subjects>
```