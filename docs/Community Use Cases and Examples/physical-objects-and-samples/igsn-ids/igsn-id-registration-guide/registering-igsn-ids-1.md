---
title: Registering IGSN IDs
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
> 🚧 Have you created an IGSN ID Catalog Repository?
> 
> An IGSN ID Catalog Repository is necessary to begin registering IGSN IDs. See [Creating an IGSN ID Catalog Repository](doc:registering-igsn-ids) to get started.

## How to register IGSN IDs

There is no functional distinction between IGSN IDs and other DOIs registered with DataCite. Thus, the same DataCite APIs used to create and modify DOIs can also be used to create and modify IGSN IDs.

IGSN IDs must be created within a designated [IGSN ID Catalog Repository](doc:registering-igsn-ids) and must be registered with the [`resourceTypeGeneral`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/resourcetype/#a-resourcetypegeneral) DataCite Metadata Schema property set to `PhysicalObject`.

We recommend using DataCite’s REST API for your institution’s IGSN ID registration processes. Please refer to the existing [DataCite REST API guide](doc:api) to determine the most appropriate implementation for your institution and workflows. You may also review our [API Reference page](ref:introduction).

Fabrica can also be used to register and modify IGSN IDs. See [Create and Update DOIs with the DOI Form](doc:fabrica-doi-form) and [Create and Update DOIs with File Upload](doc:fabrica-doi-file-upload). 

### Creating IGSN ID metadata in the DataCite Metadata Schema

IGSN IDs for material samples are registered with metadata encoded in the [DataCite Metadata Schema](doc:datacite-metadata-schema). Consult [IGSN ID Metadata](doc:igsn-id-metadata) for best practices and guidance concerning mandatory and recommended properties in the DataCite Metadata Schema. 

> 📘 
> 
> For further information about the DataCite Metadata Schema, see [DataCite Metadata Schema documentation](https://schema.datacite.org/).

### Assigning IGSN ID DOI suffixes

IGSN IDs registered with DataCite will be assigned a DOI prefix and suffix. The DOI prefix will depend on the prefix assigned to your IGSN ID Catalog Repository, and the syntax of the DOI suffix is up to your institution. In Fabrica and DataCite APIs, the system will automatically assign a random string upon creation unless a specific suffix is supplied.

The IGSN e.V. plans to develop disciplinary best practices for DOI suffixes in collaboration with a variety of samples communities as they begin to register IGSN IDs with DataCite. If you are interested in contributing to DOI suffix best practices, contact the IGSN e.V. at [info@igsn.org](mailto:info@igsn.org).  

For additional information on how your institution might implement DOI suffixes for IGSN IDs, see [the DOI Basics section on suffixes](doc:doi-basics#suffix).

> 📘 
> 
> Please consult the [IGSN–DataCite Namespaces and Prefixes Recommendation](https://docs.google.com/document/d/1x27_LzLBxHXGb8X81d3f99NoFE2JNT9LjCx-NhlEAOE/edit?usp=sharing) for an overview of the history of IGSN ID namespace governance, as well as recommendations for the future of namespace governance and resolution. The recommendation was produced by the IGSN–DataCite Namespace Working Group.

### Accommodating samples workflows where metadata may not be immediately available

Depending on your institution’s workflows for assigning IGSN IDs, you may find DataCite’s Draft state helpful. No metadata is required for Draft state. Thus, Draft state may be appropriate for workflows where identifiers are assigned in the field or in advance of sample collection. Draft state can later be changed to Registered or Findable state when at least the six mandatory DataCite metadata properties are populated. See our support documentation on [DOI states](doc:doi-states). 

The DataCite Metadata Schema also provides a set of standard values that may be used when mandatory property values are not available for various reasons. Please see [Appendix 3: Standard values for unknown information](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-3/) for more information about these values. Example standard values for unknown information include `:unac` for “temporarily inaccessible” and `:unav` for “value unavailable, possibly unknown.”

## Improving DataCite services for IGSN IDs

We are eager to understand your use cases and user needs for IGSN IDs in DataCite services. These contributions will help shape the future of DataCite’s Product Roadmap for IGSN IDs. 

Submit suggestions via the [DataCite Roadmap](doc:how-to-contact-datacite#feature-suggestions). If you are unsure if a feature already exists or if a use case is possible, please consult our [Support documentation](https://support.datacite.org/) or contact [support@datacite.org](mailto:support@datacite.org).