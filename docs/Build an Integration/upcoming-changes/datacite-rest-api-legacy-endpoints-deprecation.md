---
title: DataCite REST API Legacy Endpoints Deprecation
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
## What's changing

The legacy REST API endpoints `/works`, `/members`, and `/data-centers` will be deprecated on **1 July 2026**. 

The current version of the DataCite REST API, Version 2, was introduced in 2017. The [Version 2 functionality is documented on our Support site](doc:api) and includes endpoints like `/dois`, `/providers`, and `/clients`. 

The previous version of the REST API, Version 1,  includes legacy endpoints like `/works`, `/members`, and `/data-centers`. These endpoints are documented here: [DataCite REST API (v1)](doc:api-v1). Version 1 has not been updated or supported for several years and can not be used to create or manage DOI metadata. 

Due to the low usage of Version 1 and the improved functionality of the widely-adopted Version 2 successor, Version 1 endpoints will be deprecated on 1 July 2026. This deprecation will only affect a small number of users.

## How to transition from legacy endpoints

If you’re currently using any endpoints from Version 1 (`/works`,`/members`, or `/data-centers`), update your requests to use the equivalent Version 2 endpoints:

- `/works` → `/dois`
- `/members` → `/providers`
- `/data-centers` → `/clients`

### Transition from `/works` to `/dois`

The `/dois` endpoint contains similar functionality to the `/works` endpoint.

| Version 1 request                     | Version 2 request                    |
| :------------------------------------ | :----------------------------------- |
| `https://api.datacite.org/works`      | `https://api.datacite.org/dois`      |
| `https://api.datacite.org/works/{id}` | `https://api.datacite.org/dois/{id}` |

The response structure has several differences, including:

[block:parameters]
{
  "data": {
    "h-0": "Response section",
    "h-1": "Version 1 response (`/works`)",
    "h-2": "Version 2 response (`/dois`)",
    "0-0": "data.type",
    "0-1": "\"works\"",
    "0-2": "\"dois\"",
    "1-0": "data.attributes",
    "1-1": "Contains an incomplete DataCite DOI metadata record, with modified field names (e.g. \"author\" instead of \"creators\").",
    "1-2": "Contains the complete DataCite DOI metadata record in JSON, structured according to the [DataCite XML to JSON Mapping](doc:datacite-xml-to-json-mapping).",
    "2-0": "data.relationships",
    "2-1": "Contains \"data-center\", \"member\", and \"resource-type\" relationships.",
    "2-2": "Contains \"client\" relationships by default.  \n  \nTo include \"provider\" relationships, add the parameter `detail=true`.",
    "3-0": "meta",
    "3-1": "Contains facets for \"resource-types\", \"registered\", \"providers\", \"data-centers\", and \"affiliations\".  \n  \nContains \"total\", \"total-pages\", and \"page\" information.",
    "3-2": "Contains the facets documented here: [Retrieving a list of DOIs - What's in the API response?](doc:api-get-lists#whats-in-the-api-response)  \n  \nContains \"total\", \"totalPages\", and \"page\" information.",
    "4-0": "links",
    "4-1": "Does not contain links.",
    "4-2": "Contains links to \"self\" (current results page) and \"next\" (next results page)."
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


### Transition from `/members` to `/providers`

The `/providers` endpoint contains similar functionality to the `/members` endpoint.

| Version 1 request                       | Version 2 request                         |
| :-------------------------------------- | :---------------------------------------- |
| `https://api.datacite.org/members`      | `https://api.datacite.org/providers`      |
| `https://api.datacite.org/members/{id}` | `https://api.datacite.org/providers/{id}` |

The response structure has several differences, including:

[block:parameters]
{
  "data": {
    "h-0": "Response section",
    "h-1": "Version 1 response (`/members`)",
    "h-2": "Version 2 response (`/providers`)",
    "0-0": "data.type",
    "0-1": "\"members\"",
    "0-2": "\"providers\"",
    "1-0": "data.attributes",
    "1-1": "Contains partial metadata for DataCite Members and Consortium Organizations, including:  \n  \n- title\n- display-title\n- description\n- member-type\n- organization-type\n- focus-area\n- region\n- country\n- year\n- logo-url\n- website\n- joined\n- created\n- updated",
    "1-2": "Contains complete metadata for DataCite Members and Consortium Organizations, including:  \n  \n- name\n- displayName\n- symbol\n- website\n- description\n- region\n- country\n- logoUrl\n- memberType\n- organizationType\n- focusArea\n- nonProfitStatus\n- isActive\n- joined\n- created\n- updated\n- doiEstimate",
    "2-0": "data.relationships",
    "2-1": "Does not contain relationships.",
    "2-2": "Contains \"clients\" and \"prefixes\" relationships.",
    "3-0": "meta",
    "3-1": "Contains facets for \"years\", \"regions\", \"organization-types\", and \"focus-areas\".  \n  \nContains \"total\", \"total-pages\", and \"page\" information.",
    "3-2": "Contains facets for \"years\", \"regions\", \"memberTypes\", \"organizationTypes\", \"focusAreas\", \"nonProfitStatuses\", and \"hasRequiredContacts\".  \n  \nContains \"total\", \"totalPages\", and \"page\" information.",
    "4-0": "links",
    "4-1": "Does not contain links.",
    "4-2": "Contains links to \"self\" (current results page) and \"next\" (next results page)."
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


### Transition from `/data-centers` to `/clients`

The `/clients` endpoint contains similar functionality to the `/data-centers` endpoint.

| Version 1 request                            | Version 2 request                       |
| :------------------------------------------- | :-------------------------------------- |
| `https://api.datacite.org/data-centers`      | `https://api.datacite.org/clients`      |
| `https://api.datacite.org/data-centers/{id}` | `https://api.datacite.org/clients/{id}` |

The response structure has several differences, including:

[block:parameters]
{
  "data": {
    "h-0": "Response section",
    "h-1": "Version 1 response (`/data-centers`)",
    "h-2": "Version 2 response (`/clients`)",
    "0-0": "data.type",
    "0-1": "\"data-centers\"",
    "0-2": "\"clients\"",
    "1-0": "data.attributes",
    "1-1": "Contains partial metadata for DataCite Repositories, including:    \n  \n- title  \n- other-names  \n- prefixes  \n- member-id  \n- year  \n- created  \n  updated",
    "1-2": "Contains complete metadata for DataCite Repositories, including:    \n  \n- name  \n  -symbol  \n- year  \n- alternateName  \n- description  \n- language  \n- clientType  \n- domains  \n- re3data  \n- opendoar  \n- issn  \n- url  \n- created  \n- updated  \n- isActive",
    "2-0": "data.relationships",
    "2-1": "Contains \"member\" relationships.",
    "2-2": "Contains \"provider\", \"consortium\", and \"prefixes\" relationships.",
    "3-0": "meta",
    "3-1": "Contains facets for \"years\" and \"members\".  \n  \nContains \"total\", \"total-pages\", and \"page\" information.",
    "3-2": "Contains facets for \"years\", \"providers\", \"software\", \"certificates\", \"repository_types\", and \"clientTypes\".  \n  \nContains \"total\", \"total-pages\", and \"page\" information.",
    "4-0": "links",
    "4-1": "Does not contain links.",
    "4-2": "Contains links to \"self\" (current results page) and \"next\" (next results page)."
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]