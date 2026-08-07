---
title: How can I set up an API query to retrieve IGSN IDs?
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
An [IGSN ID](doc:igsn-ids) must be registered in an [IGSN ID Catalog Repository](doc:registering-igsn-ids) with resourceTypeGeneral “PhysicalObject”. If you want to set up a query to retrieve only DOIs that are IGSN IDs, you will need to include the client-type filter in your API query and set it to “igsnCatalog”:

<https://api.datacite.org/dois?client-type=igsnCatalog>

You can also filter to IGSN IDs in DataCite Commons using the “IGSN ID Catalog” Repository Type facet:

<https://commons.datacite.org/doi.org?query=*&repository-type=igsnCatalog>

Learn more about [registering IGSN IDs for physical samples](doc:igsn-id-registration-guide).