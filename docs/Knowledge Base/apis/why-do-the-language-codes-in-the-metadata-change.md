---
title: Why do the language codes in the metadata change?
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
When you submit [Language property](https://datacite-metadata-schema.readthedocs.io/en/4/properties/language/) metadata to DataCite in XML and JSON format, you might have noticed that there is a normalization in place which is reflected in the REST API. This means that if there is a three-letter [ISO 639-3 language code](https://www.iso.org/iso-639-language-code) or a ISO 639-1 language code with a subvalue provided, the system will automatically update it to the matching two-letter ISO 639-1 code. 

This is the expected behaviour at present, but we are aware that this can be confusing. We welcome feature requests, metadata schema feedback, and other suggestions through the [DataCite Suggestions forum on GitHub](https://github.com/datacite/datacite-suggestions/discussions/67).