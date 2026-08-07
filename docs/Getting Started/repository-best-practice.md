---
title: Repository Best Practices
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This guide is for those setting a up a new data or literature repository, or those looking to align existing repositories with current best practices.
[block:api-header]
{
  "title": "COAR Community Framework for Good Practices in Repositories"
}
[/block]
The [Confederation of Open Access Repositories (COAR)](https://www.coar-repositories.org/) provides excellent guidance on repository best practices, and their [Community Framework for Good Practices in Repositories](https://www.coar-repositories.org/coar-community-framework-for-good-practices-in-repositories/) is a great place to start when choosing a repository platform, setting up a new repository or evaluating existing repositories.
[block:api-header]
{
  "title": "Implementing COAR Framework best practices with DataCite"
}
[/block]
Several of the best practices described in the COAR Framework can be implemented through DataCite services, and many are relevant to DOI registration in some way. Below is a list of the Essential and Desired Characteristics from the [COAR Community Framework for Good Practices in Repositories](https://www.coar-repositories.org/coar-community-framework-for-good-practices-in-repositories/) that are related to DataCite DOI registration, along with implementation tips and resources.

### Discovery

#### Essential characteristics

- **1.1  The repository supports quality metadata and controlled vocabularies (discipline-based, regional or general metadata schema such as Dublin Core)**
DataCite uses its own [metadata schema](https://support.datacite.org/docs/datacite-metadata-schema-44). When registering DataCite DOIs, your repository metadata will need to be converted to the [DataCite schema](https://support.datacite.org/docs/datacite-metadata-schema-44). Repository systems that integrate directly with DataCite do this automatically, though some offer the ability to customize field mappings. If you are building a custom DataCite integration with your repository using our [APIs](https://support.datacite.org/docs/api) or [registering DOIs manually via Fabrica](https://support.datacite.org/docs/doi-fabrica), you will need to determine how metadata in your system should be mapped to DataCite's schema. We maintain a [suggested DataCite to Dublin Core mapping](https://schema.datacite.org/dc/), which is updated with every new DataCite schema release.

- **1.3  The metadata in the repository are available, even in cases when the resource is no longer available**
If a repository resource that you have registered a DOI for becomes unavailable for any reason, a "tombstone" page should be used, as DOI records cannot be deleted after they are registered. DataCite recommends that tombstone pages provide minimal metadata and a statement about why the data is no longer available. If the URL of the tombstone page is different from the URL of the original landing page, it should be updated in the corresponding DOI record. [Learn more about best practices for tombstone pages](https://support.datacite.org/docs/tombstone-pages)
*Note: In case a DOI was created in error or its metadata cannot continue to be available due to privacy, security or other serious risks, we recommend using a generic tombstone page and changing the state of the DOI from Findable to Registered, so that its metadata is no longer publicly visible in DataCite tools and services.*

- **1.4  The repository assigns a persistent identifier (PID) that points to the landing page of the resource, even in cases where the resource is not available**
DataCite is a leading global non-profit organisation that provides persistent identifiers (DOIs specifically) for research data and other research outputs. DataCite [member or consortium organisations] (https://datacite.org/become.html) can register DOIs by choosing a [repository platform that integrates with DataCite](https://support.datacite.org/docs/service-provider-software-integrations), building a custom integration using [DataCite APIs](https://support.datacite.org/docs/api) or manually registering DOIs via our [Fabrica interface](https://support.datacite.org/docs/doi-fabrica). [Learn more about how to get started with DataCite](https://support.datacite.org/docs/getting-started)

- **1.5  The repository offers a search facility and/or the metadata is indexed by external discovery services and/or aggregators**
DataCite aggregates metadata for DOIs registered using its services and makes it publicly available for discovery and [harvesting (via OAI-PMH)](https://support.datacite.org/docs/datacite-oai-pmh) by other aggregators and indexing services, such as [Google Dataset search](https://datasetsearch.research.google.com/).

- **1.6  The repository is included in one or more disciplinary or general registries of resources (e.g. Re3data, OpenDOAR or other national, regional or domain registries)**
DataCite is a partner in the [Re3data global registry of research data repositories](https://www.re3data.org/). re3data is referenced by multiple publishers in their editorial policies as the best tool to identify the most appropriate data repository and recommended in the [European Commission’s Guidelines on Open Access to Scientific Publications and Research Data in Horizon 2020](http://ec.europa.eu/research/participants/data/ref/h2020/grants_manual/hi/oa_pilot/h2020-hi-oa-pilot-guide_en.pdf). We strongly recommend that DataCite members [register with re3data](https://www.re3data.org/suggest) and [include their rer3data record in their DataCite account information](https://support.datacite.org/docs/update-repository-settings#re3data-record).

#### Desired characteristics

- **1.7  The repository supports linking between related resources such as articles, data and software (e.g. including PIDs for related resources held elsewhere)**
When registering DOIs for repository items, we strongly encourage including related resources, such as papers and software related to a dataset or published articles related to a preprint/postprint, in the [related identifiers section of your metadata](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#12-relatedidentifier). This exposes links between resources to services such as [DataCite Commons](https://support.datacite.org/docs/datacite-commons), [Crossref Event Data](https://www.crossref.org/services/event-data/) and [Scholexplorer](https://scholexplorer.openaire.eu/#/),  making it easy to do tasks like find/access related items that live in different locations, count citations, and analyze usage/impact.

- **1.9  The repository supports PIDs for authors, funders, funding programmes and grants, institutions, and other relevant entities**
In addition to including PIDs for for authors, funders, institutions, etc, in metadata stored in your repository, we strongly recommend including these PIDs in DOI metadata. Doing so allows tools/services that harvest DOI metadata to easily connect items in your repository to authors, institutions, funders and grants. Author IDs, such as ORCID, and institution IDs, such as ROR, can be included in [creator](https://support.datacite.org/docs/datacite-metadata-schema-v44-mandatory-properties#2-creator) and [contributor](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#7-contributor) elements. Funder IDs, such as Crossref Funder Registry and ROR, can be included in [fundingReference](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#19-fundingreference) elements.

- 1.12  **In the case of data, the repository supports PIDs for data at multiple levels of granularity, where appropriate (for example, if there there is research using a subset of the full dataset, a citation of the data subset will be needed)**
It's possible to create DOIs for a collection of resources, as well as  individual items within that collection. The parent collection DOI should have ```resourceTypeGeneral="Collection"``` in the resourceType element and DOIs for the items in the collection should be listed in the [relatedIdentifier section](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#12-relatedidentifier) with relationType "hasPart". DOIs for individual items in the collection should have the parent collection DOI listed in the [relatedIdentifier section](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#12-relatedidentifier) with relationType "isPartOf".

### Reuse
#### Essential characteristics

- **3.1  The repository includes licensing information in the metadata record which stipulates reuse conditions**
In addition to providing licensing information in metadata stored within your repository, we strongly recommend including it in DOI metadata sent to DataCite so that it’s available to aggregators and indexing services that harvest DataCite metadata. Licensing information can be included in the [Rights field](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#16-rights).

- **3.2  The repository provides citable PIDs (1) – see 1.4**
DOIs provide a persistent, citable URL that remains the same even when the location of the content changes. A citation for any DOI can be automatically generated in a variety of formats using the [DOI Citation Formatter Tool](https://citation.crosscite.org/), a partner service offered by DataCite, Crossref and several other DOI registration agencies. When citing datasets in publications, citations should be included in the references section, so that they are incorporated into machine-readable metadata in the resulting article DOI. This allows tools/services that consume DOI metadata to easily identify datasets related to publications. For more information about data citation best practices see [Data Citation Resources](https://support.datacite.org/docs/data-citation).

- **3.4  The landing pages include the metadata about the  item including information required for citation in machine and human readable format**
DOIs for your repository items should resolve to a publicly visible landing page, rather than directly to the items themselves. We recommend that landing pages display the DOI and citation information to users (so they know they have found the correct item) and provide a way for users to access the content or instructions for accessing, in the case of resource with access restrictions. If the location of the landing page changes (for example, due to a system migration), the URL in the corresponding DOI settings must also be updated. If you have registered a DOI for an item in your repository, and the item becomes unavailable for any reason, its landing page should remain available, but include a statement of unavailability. For more information, see [Best practices for DOI landing pages](https://support.datacite.org/docs/landing-pages).

### Integrity and authenticity
#### Essential characteristics
- **4.3  The repository supports versioning of metadata and resources after deposit**	
When metadata for an item in your repository that has a DOI is updated (for example, to correct errors or add additional details) its corresponding DOI metadata should also be updated. A new DOI should not be registered in this case. When the content of the item itself has changed (for example, a revised version of a document or a new release of software code), we recommend registering a new DOI. The new DOI should include the original DOI in the [relatedIdentifier section](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#12-relatedidentifier) with relationType "isVersionOf". Metadata for the original DOI should be updated to include the new DOI in the [relatedIdentifier section](https://support.datacite.org/docs/datacite-metadata-schema-v44-recommended-and-optional-properties#12-relatedidentifier) with relationType "hasVersion". For more information, see [Versioning](https://support.datacite.org/docs/versioning).

### Preservation
#### Essential characteristics
- **7.1  The repository (or organization that manages repository) has a long term plan for managing and funding the repository**
If you register DOIs for items in your repository, you should also consider funding and management of those DOIs in your long-term plans. DOIs are persistent identifiers (PIDs), which means that they are intended to be a permanent means of identifying and accessing a particular resource. You cannot delete or change DOIs once they have been registered. DataCite expects all members to be active stewards of the content they are assigning DOIs to. This means you need to be able to update the content and metadata. For more information, see our [DOI registration policy](https://support.datacite.org/docs/doi-registration-policy).

### Other
#### Essential characteristics

- **9.4  The repository collects and shares usage information using a standard methodology (e.g. number of views, downloads)**
If your repository collects and processes usage statistics according to the [COUNTER Code of Practice](https://www.projectcounter.org/code-of-practice-rd-sections/foreword/), we recommend that you also submit your COUNTER reports to DataCite, so that they can be included in the metadata we make publicly available to aggregators and indexing services, as to human users of our services. To learn how to send usage data to DataCite, see [Contributing Views and Downloads](https://support.datacite.org/docs/contributing).
[block:api-header]
{
  "title": "How can I implement these DataCite practices in my repository?"
}
[/block]
- Some repository software platforms support DataCite DOI registration right out of the box or via a plugin or module. These may or may not support _all_ of the practices listed above. We recommend choosing a [platform offered by a DataCite registered service provider](https://support.datacite.org/docs/service-provider-software-integrations) to ensure alignment with DOI registration best practices.
- Some repository software platforms do not support DataCite DOI registration. In that case, you can opt to build a custom integration using [DataCite APIs](https://support.datacite.org/docs/api) or manually register DOIs via our [Fabrica interface](https://support.datacite.org/docs/doi-fabrica). Several of our [registered service providers](https://datacite.org/service-providers.html) can also assist with building custom DataCite integrations.
- If the repository platform you're using does not support DataCite DOI registration, or does not meet the best practices above, we can help you to advocate for DOI registration features. Please contact us at [info@datacite.org](mailto:info@datacite.org).
[block:api-header]
{
  "title": "Ready to get started registering DOIs?"
}
[/block]
Your organization must be a DataCite member or consortium organization in order to register DOIs.

### If your organization _is not_ a member or consortium organization
- [See our brochure](https://support.datacite.org/docs/datacite-brochure) for an overview of our services and membership structure
- Learn more about [membership options](https://datacite.org/become.html) and our [member fee model](https://datacite.org/feemodel.html)
- See our [list of DataCite consortia](https://support.datacite.org/docs/datacite-consortia) to check whether membership through a consortium is an option for you
- Review our [DOI registration policy](https://support.datacite.org/docs/doi-registration-policy) to make sure DataCite is a good fit for your repository
- If you have questions about membership, contact us at info@datacite.org

### If your organization _is_ a member or consortium organization
- See our [Getting started article](https://support.datacite.org/docs/getting-started) and our [Getting started quick guide](https://support.datacite.org/docs/getting-started-quick-guide)
- If you are registering DOIs through a repository platform integration, see the documentation for that system for configuration information.
- For help, contact us at  [support@datacite.org](mailto:support@datacite.org). For help with a specific repository platform integration, please contact the support desk for that system (DataCite does not develop these integrations, therefore it's difficult for us to provide in-depth support). Consortium organizations should first contact their consortium lead for support.