---
title: How do I retrieve DOIs in draft state with the REST API?
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
To see the draft DOIs in the response, you need to authenticate, otherwise you will only see the public facing DOIs (in findable state) 

For example, you can retrieve all the DOIs from the command line with [cURL](https://curl.haxx.se/docs/manpage.html) as follows:

```shell
curl -X GET -H "Content-Type: application/vnd.api+json" --user YOUR_CLIENT_ID:YOUR_PASSWORD https://api.test.datacite.org/dois​
```