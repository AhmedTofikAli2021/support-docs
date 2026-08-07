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
When creating a DOI, if you are seeing the message "Please enter a URL that is allowed in the domains settings of the repository" you need to check the repository domain settings in your repository account as follows:

1.  Log in with your repository account credentials
2. Under the settings tab click on "update repository"
3. Scroll down to see the domain settings for your repository and update as required.
4. you can also update the repository when logged into Fabrica with your member/consortium organization account.

Make sure all possible domain names are separated by a comma, and that there is no space before or after the comma. When you use the wildcard *, make sure it is for a subdomain and followed by a dot and the rest of the domain. Remember that this field is optional, remove the filter and allow your DOIs to point to any URL by including only the wildcard * in the domain field.

More information [here](doc:update-repository-settings)