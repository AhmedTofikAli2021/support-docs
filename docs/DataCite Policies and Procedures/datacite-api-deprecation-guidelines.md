---
title: DataCite API Deprecation Guide
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
DataCite provides a number of APIs, including the DataCite [REST API](https://support.datacite.org/docs/api) as well as the [MDS](https://support.datacite.org/docs/mds-api-guide), [GraphQL](https://support.datacite.org/docs/datacite-graphql-api-guide), [OAI-PMH](https://support.datacite.org/docs/datacite-oai-pmh), [Usage Reports](https://support.datacite.org/docs/usage-reports-api-guide), [Content Negotiation](https://support.datacite.org/docs/datacite-content-resolver) and [Event Data APIs](https://support.datacite.org/docs/eventdata-guide). DataCite strives to avoid API changes that disrupt existing functionality and require code changes for compatibility. However, in some circumstances, DataCite may introduce deprecations to DataCite APIs based on community needs and DataCite organizational priorities. This guide details the process for deprecating API functionality to allow the DataCite community to adapt to changes with minimal disruption.

## What do we mean by breaking change and deprecation?

A deprecation is a planned breaking change. A breaking change is a non-backward-compatible change to existing API behavior.

A breaking change may remove, rename, or move data within a response or invalidate previously valid API requests. Examples of breaking changes include:

- Removing, renaming, or modifying the data type of an object in a response.  
- Making backward incompatible changes to the submission validation of a field.  
- Removing an API endpoint.

## When will breaking changes happen?

In all possible circumstances, DataCite will avoid deprecations with measures like API versioning, backward compatible changes, and user-configurable requests. However, deprecations may be implemented under the following circumstances:

- Existing functionality has been significantly improved by new functionality.  
- Functionality is no longer efficient, secure or scalable.   
- Functionality no longer aligns with DataCite’s strategic goals or community requirements.  
- Functionality has low usage.

## How will I know when a breaking change is going to happen?

DataCite will use the following channels to notify users of upcoming deprecations: 

- [DataCite Status Page](https://status.datacite.org/)  
- DataCite Support Site, including the [API Reference](https://support.datacite.org/reference/introduction) and [applicable documentation](https://support.datacite.org/)  
- Email communication with:  
  - DataCite Members  
  - DataCite [Registered Service Providers](https://datacite.org/service-providers/)  
- Targeted outreach (where possible)

> 🚧 
> 
> It is your responsibility as a DataCite Member, Consortium Lead or Consortium Organization to ensure that correct and up to date contact information has been added to your organization’s [contact list in DataCite Fabrica](https://support.datacite.org/docs/fabrica-contacts).

## How much notice should I expect when an API deprecation is planned?

We strive to notify users of deprecations within the timeframes below.

[block:parameters]
{
  "data": {
    "h-0": "Deprecation type",
    "h-1": "Advance notice timeframe",
    "0-0": "Minor changes such as:  \nChanges that are backward compatible with user configuration; for example, by updating a URL query or header.",
    "0-1": "6 months",
    "1-0": "Significant changes such as:  \nRemoving, renaming, or modifying the data type of an object in a response.  \nMajor submission validation changes, like the deprecation of support of a DataCite Metadata Schema version.  \nRetiring endpoints with low community use.",
    "1-1": "12 months",
    "2-0": "Major changes such as:  \nRetiring the previous version of an API endpoint after a new API version has been introduced.  \nRetiring endpoints with significant community use.",
    "2-1": "24 months",
    "3-0": "Changes that involve:  \nUrgent security concerns.  \nUrgent infrastructural concerns.",
    "3-1": "Case-by-case"
  },
  "cols": 2,
  "rows": 4,
  "align": [
    "left",
    "left"
  ]
}
[/block]


> 👍 
> 
> We would be happy to hear from you if you have any questions about API deprecations. Please contact [support@datacite.org](mailto:support@datacite.org).