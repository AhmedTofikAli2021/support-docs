---
title: When should I use the standard value “:etal” when entering “Creator” metadata?
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
The DataCite metadata schema includes a list of [standard values](doc:datacite-metadata-schema-v44-standard-values-for-unknown-information). These values are intended to be used when the mandatory property values are not available for various reasons. In a scenario where there are a large number of creators e.g. >20 , the “:etal” standard value can be used to replace a subset of the “Creators”.

For example, if there are 20 Creators, the names can be included for the first 10 and then “:etal” for the 11th Creator.