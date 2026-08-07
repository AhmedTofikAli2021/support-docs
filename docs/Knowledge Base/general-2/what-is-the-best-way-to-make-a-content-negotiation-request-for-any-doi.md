---
title: >-
  What is the best way to make a content negotiation request for a DOI from any
  Registration Agency?
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
Content negotiation is possible for all DOI Registration Agencies (e.g. DataCite and Crossref) via [doi.org](http://google.com). Following the guidance [outlined in the documentation](https://support.datacite.org/docs/datacite-content-resolver), you can make a content negotiated request like this:

```shell
curl -LH "Accept: application/vnd.citationstyles.csl+json;q=1.0" https://doi.org/10.1021/acs.joc.0c00770
```

DataCite's content negotiation service is available at <https://data.datacite.org> and only supports DataCite DOIs.