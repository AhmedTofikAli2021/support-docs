---
title: Why is my URL not allowed by the repository domain settings?
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
When creating a DOI, if you are seeing the message "Please enter a URL that is allowed in the domains settings of the repository", check the [Domain settings](doc:fabrica-settings#domains) in your Repository account.

1. Log in with your Repository account credentials.
   1. You can also update the Repository when logged into Fabrica with your Direct Member or Consortium Organization account.
2. Under the Settings tab, click "Update repository".
3. Scroll down to see the domain settings for your Repository and update as required.

Make sure all possible domain names are separated by a comma, and that there is no space before or after the comma. When you use the wildcard `*`, make sure it is for a subdomain and followed by a dot and the rest of the domain. Remember that this field is optional. By removing the filter, you allow your DOIs to point to any URL by including only the wildcard `*` in the domain field.