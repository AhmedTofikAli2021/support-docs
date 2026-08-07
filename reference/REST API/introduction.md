---
title: REST API
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
## Version History

* v.1: June 25, 2016, first draft.
* v.1.1: October 10, 2016, follow JSONAPI spec for side-loading associations
* v.1.2: December 9, 2017, follow JSONAPI spec for pagination
* v.2.0: January 7, 2019, new API endpoints, using camelCase for attributes

## Overview

The DataCite REST API returns information about DataCite content. The API is RESTFUL and returns results in JSON. It follows the [JSONAPI](http://jsonapi.org/) specification. The mime-type for API results is `application/vnd.api+json`. 

More information about the DataCite REST API can be found in the [REST API Guide](doc:api).