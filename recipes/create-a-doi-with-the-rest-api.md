---
title: Create a DOI with the REST API
description: Recipe Description
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```shell Shell
curl --request POST \
     --url https://api.test.datacite.org/dois \
     --header 'authorization: Basic PDx1c2VyPj46PDxwYXNzPj4=' \
     --header 'content-type: application/json'
```

```json Response Example
{"success":true}
```

# Create a POST request



