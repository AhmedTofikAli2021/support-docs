---
title: DataCite REST API "affiliation" and "publisher" Default Change
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
## What’s changing?

By default, requests to the `/dois` endpoint will include full affiliation and publisher details, including [affiliation identifiers](https://datacite-metadata-schema.readthedocs.io/en/4/properties/creator/#a-affiliationidentifier) (for creators and contributors) and [publisher identifiers](https://datacite-metadata-schema.readthedocs.io/en/4/properties/publisher/#a-publisheridentifier) when available. 

**The new default will match the response you currently get when you include `affiliation=true` and `publisher=true` in your request**. 

This change will take effect in **September 2027**.

## Why are we making this change?

We’re making this change so that full affiliation and publisher details are accessible by default, without having to include a parameter. 

When affiliationIdentifier and publisherIdentifier were first introduced, we prioritized backward compatibility for REST API users over returning a full metadata record. Now that both affiliationIdentifier and publisherIdentifier have significant adoption—33% of DataCite DOIs have an affiliationIdentifier, and 42% have a publisherIdentifier—we want to ensure that metadata consumers aren’t missing this information. 

As affiliation and publisher identifiers are increasing in importance, we are fielding more questions about why they’re “missing” from queries—when the information is actually there, but not exposed by default. By changing the default, we will simplify the API requests required to return complete DataCite DOI metadata records.

## How the affiliation and publisher parameters work

DataCite Metadata Schema 4.3 added sub-properties to _affiliation_ for _affiliationIdentifier_, _affiliationIdentifierScheme_, and _schemeUri_. To accommodate these properties in the REST API, we updated the _affiliation_ representation from a list of strings to a list of objects. Because this was a breaking change, we introduced a new query parameter `affiliation=true`. 

With `affiliation=true` in the request, the response includes a list of objects for affiliation with the nested sub-properties:

#### Full affiliation metadata (new default in September 2027 and with `affiliation=true`)

```json
"affiliation": [  
  {  
    "name": "United States Geological Survey",  
    "schemeUri": "https://ror.org",  
    "affiliationIdentifier": "https://ror.org/035a68863",  
    "affiliationIdentifierScheme": "ROR"  
  }  
]
```

Currently, without `affiliation=true` in the request, or by passing `affiliation=false`, affiliation is returned in its original representation as a list of strings:

#### Partial affiliation metadata (current default and with `affliliation=false`)

```json
"affiliation": ["United States Geological Survey"]
```

Similarly, DataCite Metadata Schema 4.5 added sub-properties to _publisher_ for _publisherIdentifier_, _publisherIdentifierScheme_, and _schemeUri_. To accommodate these properties in the REST API, we updated the publisher representation from a string to an object and introduced a new query parameter `publisher=true`.

With `publisher=true` in the request, the response includes an object for publisher with the nested sub-properties:

#### Full publisher metadata (new default in September 2027 and with`publisher=true`)

```json
"publisher": 
  {  
    "name": "Dryad",  
    "schemeUri": "https://ror.org",  
    "publisherIdentifier": "https://ror.org/00x6h5n95",  
    "publisherIdentifierScheme": "ROR"
  }  

```

Currently, without `publisher=true` in the request, or by passing `publisher=false`, publisher is returned in its original representation as a string:

#### Partial publisher metadata (current default and with `publisher=false`)

```json
"publisher": "Dryad"
```

For more information, see: [Can I see more detailed affiliation and publisher information in the REST API?](doc:can-i-see-more-detailed-affiliation-information-in-the-rest-api)

## How to update your requests

### To include full affiliation and publisher details

If you are already making requests with the `affiliation=true` and `publisher=true` URL parameters, no change is required. When the default switches in September 2027, setting these parameters will no longer have any effect and may be omitted to streamline your queries.

If you would like to start retrieving full affiliation and publisher details, you can add `affiliation=true` and `publisher=true` to your REST API requests. This will align the response you receive with the new default after September 2027.

[block:parameters]
{
  "data": {
    "h-0": "Request type",
    "h-1": "Include affiliation and publisher details in the response - until September 2027",
    "h-2": "Include affiliation and publisher details in the response - after September 2027",
    "0-0": "**List of DOIs**",
    "0-1": "`https://api.datacite.org/dois?affiliation=true&publisher=true`",
    "0-2": "`https://api.datacite.org/dois`  \n  \nOR  \n  \n`https://api.datacite.org/dois?affiliation=true&publisher=true`",
    "1-0": "**Single DOI**",
    "1-1": "`https://api.datacite.org/dois/10.5438/fdqk-vc49?affiliation=true&publisher=true`",
    "1-2": "`https://api.datacite.org/dois/10.5438/fdqk-vc49`  \n  \nOR  \n  \n`https://api.datacite.org/dois/10.5438/fdqk-vc49?affiliation=true&publisher=true`"
  },
  "cols": 3,
  "rows": 2,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


### To exclude full affiliation and publisher details

If you are not making requests with the `affiliation=true` and `publisher=true` URL parameters, and you do not want the response structure to change, you can add `affiliation=false` and `publisher=false` to your REST API requests.

[block:parameters]
{
  "data": {
    "h-0": "Request type",
    "h-1": "Exclude affiliation and publisher details from the response - until September 2027",
    "h-2": "Exclude affiliation and publisher details from the response - after September 2027",
    "0-0": "**List of DOIs**",
    "0-1": "`https://api.datacite.org/dois`  \n  \nOR  \n  \n`https://api.datacite.org/dois?affiliation=false&publisher=false`",
    "0-2": "`https://api.datacite.org/dois?affiliation=false&publisher=false`",
    "1-0": "**Single DOI**",
    "1-1": "`https://api.datacite.org/dois/10.5438/fdqk-vc49`  \n  \nOR  \n  \n`https://api.datacite.org/dois/10.5438/fdqk-vc49?affiliation=false&publisher=false`",
    "1-2": "`https://api.datacite.org/dois/10.5438/fdqk-vc49?affiliation=false&publisher=false`"
  },
  "cols": 3,
  "rows": 2,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]