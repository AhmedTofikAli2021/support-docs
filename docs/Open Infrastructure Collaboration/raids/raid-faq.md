---
title: RAiD FAQ
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
**Do I need to be a DataCite Member to register RAiDs?**  
RAiDs are registered through RAiD Registration Agencies (RAs) that use the DataCite infrastructure. You can contact ARDC at [contact@raid.org](mailto:contact@raid.org) to discuss how you can get started with RAiD registration.

**How do I find the right RAiD Registration Agency for me?**  
Please contact [support@datacite.org](mailto:support@datacite.org) and we can point you to the relevant Registration Agency. If you are interested in starting a new RAiD RA, please contact ARDC at [contact@raid.org](mailto:contact@raid.org).

**Which resource type will be used in the DataCite metadata schema when registering a RAiD?**  
RAiDs will be registered by RAiD Registration Agencies through DataCite’s standard processes with the [resourceTypeGeneral "Project"](https://schema.datacite.org/).

**Is it possible to distinguish RAiDs from other DOIs?**  
RAiDs are registered in a RAiD-specific repository type called “RAiD Registry.” It is possible to filter (or limit) RAiDs in API calls by specifying the repository type. [See the API documentation](https://support.datacite.org/reference/get_clients). RAiDs can also be searched in DataCite Commons by specifying the repository type (client.client_type:raidRegistry). [See documentation on Commons searches](doc:datacite-commons-search). RAiDs will resolve to the RAiD landing pages via raid.org.