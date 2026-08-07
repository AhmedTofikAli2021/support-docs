---
title: EventData Query API for Data Usage
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
This guide is intended to get you up-and-running with a real-world EventData Query API example for data usage. We'll cover all of the essentials that you need to know, from authentication to retrieving results, to filtering records. In this guide, we will cover DataCite Usage exclusively.

Most applications will use an existing wrapper library in the language of your choice, but it's important to familiarize yourself with the underlying API HTTP methods first. There's no easier way to kick the tires than through cURL.

In the rest of this guide, we will run an example using the DOI `10.7291/d1q94r` and retrieving events/links from the `datacite-usage` source. Let's start by testing our setup. In this guide, the examples we will use will employ the Test EventData endpoint (i.e., https://api.test.datacite.org/events ). When you want to work with the production environment you will just need to use the production endpoint (i.e., https://api.datacite.org/events ).

## Retrieving relationships by DOI name

To retrieve DOI links we need to call the `events` resource and filter by the *DataCite Usage* `source` and the *DOI name*. To filter by DOI name in this case we will use the `DOI` filter. 

```shell
  curl "https://api.test.datacite.org/events?mailto=YOUR_EMAIL_HERE&source-id=datacite-usage&doi=10.5061/dryad.n81g1" 
```

```json
  {
    data: [{
      id: "8a7b0a30-6638-4544-8935-61e42c02fa61",
      type: "events",
      attributes: {
        subj-id: "https://api.test.datacite.org/reports/2018-3-Dash",
        obj-id: "https://doi.org/10.7291/d1q94r",
        message-action: "add",
        source-token: "28276d12-b320-41ba-9272-bb0adc3466ff",
        relation-type-id: "total-dataset-investigations-regular",
        source-id: "datacite-usage",
        total: 3,
        license: "https://creativecommons.org/publicdomain/zero/1.0/",
        occurred-at: "2128-04-09T00:00:00.000Z",
        timestamp: "2018-05-09T13:53:47Z",
        subj: {
          pid: "https://api.test.datacite.org/reports/2018-3-Dash",
          issued: "2128-04-09"
        },
        obj: {}
      }
    }],
    links: {
      self: "https://api.test.datacite.org/events?doi=10.7291%2Fd1q94r&page%5Bnumber%5D=1&page%5Bsize%5D=25&source-id=datacite-usage",
      first: "https://api.test.datacite.org/events?doi=10.7291%2Fd1q94r&page%5Bnumber%5D=1&page%5Bsize%5D=25&source-id=datacite-usage",
      prev: null,
      next: null,
      last: "https://api.test.datacite.org/events?doi=10.7291%2Fd1q94r&page%5Bnumber%5D=1&page%5Bsize%5D=25&source-id=datacite-usage"
    },
    meta: {
      total: 70,
      total-pages: 2,
      page: 1
    }
  }
```

Mmmmm, tastes like JSON. More importantly, this is a JSONAPI response. For more information about the JSOAPI specification please visit http://jsonapi.org/recommendations/. The JSONAPI responses have three main objects: `data`, `links` and `meta`. We will focus on the `data` object, as this object contains all the information we want and its provided from the `DataCite Usage` source. There are a few important things to consider. First, the attribute `data`  is an array and contains the metadata for all the usage metrics for the DOI found by the query. Usually, you will find a maximum of 8 events/links per DOI in this array. One for each metric_type and access_method permutation. For more information about the meaning of these attributes please have a look at the [Code of Practice for Data Usage](https://peerj.com/preprints/26505/). We will take a look at this further down in this guide. But first, we will take a look at the attributes of the events in the next section. Having said that, at this point you now know how to use the EventData Query API to retrieve Usage Reports-to-DOI events/links.


## Links Provided by MakeDataCount Hub in Event Data


The data from this source includes all events/links in Data Usage Reports deposited by DataCite DOI service providers. Where a relation is made between a DataCite DOI and a Data Usage Report, that link is sent in an Event. In the example for the DOI `10.7291/d1q94r`, an event looks like this:

```json
    data: [{
      id: "8a7b0a30-6638-4544-8935-61e42c02fa61",
      type: "events",
      attributes: {
        subj-id: "https://api.test.datacite.org/reports/2018-3-Dash",
        obj-id: "https://doi.org/10.7291/d1q94r",
        message-action: "add",
        source-token: "28276d12-b320-41ba-9272-bb0adc3466ff",
        relation-type-id: "total-dataset-investigations-regular",
        source-id: "datacite-usage",
        total: 3,
        license: "https://creativecommons.org/publicdomain/zero/1.0/",
        occurred-at: "2128-04-09T00:00:00.000Z",
        timestamp: "2018-05-09T13:53:47Z",
        subj: {
          pid: "https://api.test.datacite.org/reports/2018-3-Dash",
          issued: "2128-04-09"
        },
        obj: {}
      }
    }],
```

Each Event is a JSON-representable object. Events have a core set of fields as described below.

| Field              | Type        | Optional? | Description |
|--------------------|-------------|-----------|-------------|
| `subj_id`          | URI         | No  | Usage Report Persistent ID. |
| `obj_id`           | URI         | No  | Dataset Persistent ID (DataCite DOI). |
| `subj`          | JSON Object | Yes  | Metadata about the Usage Report. |
| `obj`          | JSON Object | Yes  | Metadata about the DOI|
| `timestamp`        | Timestamp   | No  | Timestamp of when the Event was created. |
| `occurred_at`      | Timestamp   | No  | Timestamp of when the Event is reported to have occurred |
| `id`               | UUID        | No  | Unique ID for the Event |
| `total`               | integer        | No  | Number of total counts |
| `source_id`        | string      | No  | A name for the source. In this case, this is DataCite-Usage |
| `source_token`     | UUID        | No  | Unique ID that identifies the Agent that generated the Event. |
| `relation_type_id` | string      | No  | Type of the relationship between the subject and object. The types found in the Code of Practice for Data Usage](https://peerj.com/preprints/26505/) |

In the example above, we can see that the event represents a relationship between a DataCite DOI and a Data Usage Report, that this relationship was created in `2017-03-10` but it was captured by EventData Service in `2017-05-18`. Additionally, we know that the relation type indicated that the link between the  DataCite DOI `10.7291/d1q94r` and the Usage Report represent the type of metric ( `total-dataset-investigations') and type of access( `regular`), to the Resource represented by the DataCite DOI and that there is a `total` of 3 counts for this type of metric and access type.

### Relation Types

There eight relation types between usage reports and DataCite DOIs. These relation types are the permutations of  metric_type and access_method.

| Relation Type              | Type        | Description |
|--------------------|-------------|---------------------|
| total-dataset-investigations-regular          | Integer         | Counts for total-dataset-investigations using the regular access method |
| total-dataset-investigations-machine          | Integer         | Counts for total-dataset-investigations using the machine access method |
| total-dataset-requests-regular          | Integer         | Counts for total-dataset-requests using the regular access method |
| total-dataset-request-machine          | Integer         | Counts for total-dataset-requests using the machine access method |
| unique-dataset-investigations-regular          | Integer         | Counts for unique-dataset-investigations using the regular access method |
| unique-dataset-investigations-machine          | Integer         | Counts for unique-dataset-investigations using the machine access method |
| unique-dataset-requests-regular          | Integer         | Counts for unique-dataset-requests using the regular access method |
| unique-dataset-request-machine          | Integer         | Counts for unique-dataset-requests using the machine access method |

## Authentication: Tell us who you are

Please also send the `mailto` query parameter. **It is not compulsory**, but will help us understand how people are using the API and we can get in touch if we need to. We won't share your email address and will only contact you in connection with API use. For example: 

```shell
curl "https://api.test.datacite.org/events?mailto=YOUR_EMAIL_HERE&source=datacite-usage&subj-id=10.7291/d1q94r&relation-type=total-dataset-investigations-regular"
```

If you are uncomfortable sending a contact email address, then don't. You can [read more about the rationale here](https://github.com/CrossRef/rest-api-doc#etiquette).



Woot! Now you know the basics of the EventData Query API for Data Usage!

- Retrieving DataCite DOIs events/links for Data Usage
- Filtering by DataCite Usage source and relationship types