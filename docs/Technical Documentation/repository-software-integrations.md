---
title: Repository Software Integrations
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
Many repository or publication platforms provide built-in DataCite integrations. In this way, you can easily start registering DOIs names for your content through DataCite.
[block:callout]
{
  "type": "info",
  "title": "To register DOI names you need a DataCite account!",
  "body": "You will have to become a DataCite Member or User in order to assign DataCite DOIs to your datasets. Check what is the difference and how to become a member [here](doc:what-is-the-difference-between-members-and-users)!"
}
[/block]
We can help you configuring these platforms, but for specific issues you should contact the developers of these integrations directly. 
[block:api-header]
{
  "title": "CKAN"
}
[/block]
[https://ckan.org](https://ckan.org)

CKAN is a data management system that makes data accessible – by providing tools to streamline publishing, sharing, finding and using data. CKAN is aimed at data publishers (national and regional governments, companies and organizations) wanting to make their data open and available.

CKAN has an extension for assigning a digital object identifier (DOI) to datasets, using the DataCite DOI service:
[http://extensions.ckan.org/extension/doi/](http://extensions.ckan.org/extension/doi/)
[block:api-header]
{
  "type": "basic",
  "title": "Dataverse"
}
[/block]
[http://dataverse.org](http://dataverse.org) 

Dataverse is an open source web application to share, preserve, cite, explore, and analyze research data. It facilitates making data available to others, and allows you to replicate others' work more easily. Researchers, data authors, publishers, data distributors, and affiliated institutions all receive academic credit and web visibility.

Dataverse supports DataCite DOIs. You can configure your installation following this guide: [http://guides.dataverse.org/en/latest/installation/config.html?highlight=datacite](http://guides.dataverse.org/en/latest/installation/config.html?highlight=datacite) 
[block:api-header]
{
  "type": "basic",
  "title": "DSpace"
}
[/block]
[http://www.dspace.org](http://www.dspace.org) 

DSpace is an open source software platform that enables organisations to:
* capture and describe digital material using a submission workflow module, or a variety of programmatic ingest options
* distribute an organisation's digital assets over the web through a search and retrieval system
* preserve digital assets over the long term.

Please, read carefully the DSpace documentation. There are some limitations on the way you can test your configuration (i.e. the test prefix is not supported!):
[https://wiki.duraspace.org/display/DSDOC6x/DOI+Digital+Object+Identifier](https://wiki.duraspace.org/display/DSDOC6x/DOI+Digital+Object+Identifier) 
[block:api-header]
{
  "title": "Eprints"
}
[/block]
[http://www.eprints.org](http://www.eprints.org/uk/)

EPrints is an open-source digital repository platform. Developed at the University of Southampton, EPrints has been providing services for over 15 years.

EPrints provides multiple plugins to mint DOIs with DataCite, you can find them here:
[http://bazaar.eprints.org/307/](http://bazaar.eprints.org/307/)
[http://bazaar.eprints.org/380/](http://bazaar.eprints.org/380/)
[https://github.com/eprints/datacite](https://github.com/eprints/datacite)
[block:api-header]
{
  "type": "basic",
  "title": "Figshare"
}
[/block]
[https://figshare.com](https://figshare.com) 

figshare is a repository where users can make all of their research outputs available in a citable,
shareable and discoverable manner.

Figshare provides DataCite DOIs as part of their Figshare for institutions service:
[https://figshare.com/services/institutions](https://figshare.com/services/institutions) 
[block:api-header]
{
  "title": "Hydra"
}
[/block]
[https://projecthydra.org](https://projecthydra.org)

Hydra is an open-source digital repository software product. Hydra's main components are Fedora Commons, Solr, Blacklight, and HydraHead.

See how Hydra manages persistent identifiers here:
[https://github.com/projecthydra-labs/hydra-remote_identifier](https://github.com/projecthydra-labs/hydra-remote_identifier)
[block:api-header]
{
  "type": "basic",
  "title": "Invenio"
}
[/block]
[http://invenio-software.org](http://invenio-software.org) 

Invenio is an open source software library management package that provides the tools for management of digital assets in an institutional repository. The software is typically used for open access repositories for scholarly and/or published digital content and as a digital library. Invenio is developed at CERN and freely available for download.

Invenio supports DataCite DOIs. You can configure your installation following this guide:
[https://datacite.readthedocs.io/en/latest/](https://datacite.readthedocs.io/en/latest/) 
[block:api-header]
{
  "title": "Islandora"
}
[/block]
Islandora is an open-source software framework designed to help institutions and organizations and their audiences collaboratively manage, and discover digital assets using a best-practices framework. Islandora was originally developed by the University of Prince Edward Island's Robertson Library, but is now implemented and contributed to by an ever-growing international community.

A few modules can be found, probably outdated:
[https://github.com/discoverygarden/islandora_doi](https://github.com/discoverygarden/islandora_doi)
[https://github.com/roblib/islandora_datacite_doi](https://github.com/roblib/islandora_datacite_doi)
[block:api-header]
{
  "title": "OJS"
}
[/block]
[https://pkp.sfu.ca/ojs/](https://pkp.sfu.ca/ojs/)

Open Journal Systems (OJS) is a journal management and publishing system that has been developed by the Public Knowledge Project through its federally funded efforts to expand and improve access to research.

OJS supports DOIs for issues, articles, galleries and supplementary files:
[https://github.com/pkp/ojs/tree/master/plugins/importexport/datacite](https://github.com/pkp/ojs/tree/master/plugins/importexport/datacite)
[block:api-header]
{
  "title": "Pure"
}
[/block]
[https://www.elsevier.com/solutions/pure](https://www.elsevier.com/solutions/pure)

Pure aggregates organization's research information from numerous internal and external sources. It is a centralized system that builds reports, carry out performance assessments, manage researcher profiles, enable research networking and expertise discovery and more.

Pure can manage the DOI registration process.
[block:api-header]
{
  "type": "basic",
  "title": "Others?"
}
[/block]
[Contact us](doc:how-to-contact-datacite) to list your integration/documentation here!
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]