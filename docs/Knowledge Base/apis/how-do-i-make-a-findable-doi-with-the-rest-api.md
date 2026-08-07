---
title: How do I make a “findable” DOI with the REST API?
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
DataCite DOIs can be created in three states “draft”, “registered” or “findable”. If you are using the REST API to create DOIs you need to specify the “event” attribute in the JSON payload. This corresponds to the action you want to trigger. To create a DOI in findable state, the required action is "publish". You need to make sure you include the URL and all of the required DOI metadata fields (DOI, creators, title, publisher, publicationYear, resourceTypeGeneral).

For example

```json
"event": "publish"
```

Possible actions:

publish - Triggers a state move from draft or registered to findable

register - Triggers a state move from draft to registered

hide - Triggers a state move from findable to registered

We recommend incorporating draft state into your workflow, which can be deleted. Findable and registered DOIs cannot be deleted.

For more information and examples [see](doc:api-create-dois#section-create-a-findable-doi)