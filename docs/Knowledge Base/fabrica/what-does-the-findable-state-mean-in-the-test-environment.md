---
title: What does the “findable” state mean in the test environment?
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
The DataCite test and production environments are completely separate. The test environment works like a sandbox and nothing you do there will ever go live in production. Test DOIs are never registered with the global handle server. Instead, findable DOIs in the test environment are registered in our sandbox handle system, which allows us to mirror the production environment.

You can read more about testing [here](doc:testing-guide)

Need a test account? Contact [support@datacite.org](mailto:support@datacite.org)