---
title: >-
  How can I see the distribution of DOI records by the Work Type
  (resourceTypeGeneral)?
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
In the [DataCite Metadata Schema](https://schema.datacite.org/) resourceTypeGeneral is one of the six mandatory properties with a controlled vocabulary list of 28 different values that describe the resource. The list includes values like Dataset, Sound, and Model. The easiest way to see the distribution of DOIs by resourceTypeGeneral is via the REST API.

You can run an unqualified API call like this: <https://api.datacite.org/dois>

At the bottom of the response you will see the meta values in "resourceTypes" contain information about the number of DOIs for the top 10 controlled vocabulary values.