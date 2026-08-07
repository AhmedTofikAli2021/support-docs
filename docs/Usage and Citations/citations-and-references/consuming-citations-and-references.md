---
title: Consuming Citations and References
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: data-citation-1
      title: Data Citation
---
Find citation information in the following DataCite services.

> 📘 
> 
> Learn more about the [sources of citation information in DataCite services](doc:what-are-the-sources-of-citation-information-in-datacite-services).

## DataCite Commons

[DataCite Commons](https://commons.datacite.org/) is a discovery, analytics, and reporting tool that harnesses the links among resources, people, and organizations found in DataCite DOI metadata and other aggregated sources. You can view citation totals and reports in DataCite Commons.

The individual [Work record](https://support.datacdoc:works-in-datacite-commons#connections) includes a total number of citations for that DOI as well as options for exploring works that cite the primary DOI. You can also see aggregated information about citations in DataCite Commons by [organization](doc:organizations-in-datacite-commons), [person](doc:people-in-datacite-commons), or [repository](doc:repository-finder). 

## DataCite Event Data

[DataCite Event Data](doc:eventdata-guide) collects and exposes links to DataCite DOIs. When a DataCite DOI is updated to add a related identifier with one of the relationTypes for citations (IsCitedBy/IsReferencedBy/IsSupplementTo) or references (Cites/References/IsSupplementedBy), a corresponding event is created. Data citation events are also imported from the Crossref data citation endpoint.

Event Data contains a list of events in the “data” section. Here is an example of an `is-cited-by` event: <https://api.datacite.org/events?doi=10.5061/dryad.qjq2bvqhq> 

```json
{
  "id": "297c9886-5f6b-4638-82bd-b67973677117",
  "type": "events",
  "attributes": {
    "subj-id": "https://doi.org/10.5061/dryad.qjq2bvqhq",
    "obj-id": "https://doi.org/10.1007/s10336-022-01988-z",
    "source-id": "datacite-crossref",
    "relation-type-id": "is-cited-by",
    "total": 1,
    "message-action": "create",
    "source-token": "28276d12-b320-41ba-9272-bb0adc3466ff",
    "license": "https://creativecommons.org/publicdomain/zero/1.0/",
    "occurred-at": "2022-05-30T05:37:36.000Z",
    "timestamp": "2022-05-30T05:37:37.828Z"
  },
  "relationships": {
    "subj": {
      "data": {
        "id": "https://doi.org/10.5061/dryad.qjq2bvqhq",
        "type": "objects"
    	}
    },
    "obj": {
      "data": {
        "id": "https://doi.org/10.1007/s10336-022-01988-z",
        "type": "objects"
      }
    }
  }
}
```

This event stems from this relatedIdentifier in the DOI metadata for the subject DOI, 10.5061/dryad.qjq2bvqhq:

```xml
<relatedIdentifier relationType="IsCitedBy" relatedIdentifierType="DOI">https://doi.org/10.1007/s10336-022-01988-z</relatedIdentifier>
```

> 📘 Why does the Event Data response not always match the DataCite DOI metadata for a given DOI?
> 
> Event data consists of a series of events over time. If the Event Data response does not match the current DataCite DOI metadata, there could be a number of reasons for this:
> 
> - Removing a related identifier from the DataCite DOI metadata does not remove the corresponding event from event data.
> - Similarly, updating the DataCite DOI metadata may result in a duplicate event being added to Event Data. This duplicate event will not be counted twice in citation/reference counts.
> - Event Data also includes linking events that originated from other related DOIs, from both DataCite and Crossref. These events will have the given DOI as the object (“obj-id”).
> - Event Data only includes linking events between DOIs and DOIs and DOIs and URLs. Other types of relatedIdentifiers are not included.

> 🚧 
> 
> At this time, events sourced from Crossref only include links between scholarly literature and datasets. These links are pulled from Crossref's [Scholix index](https://www.eventdata.crossref.org/guide/app-scholix/). DataCite users can still create relationships between DataCite DOIs and Crossref DOIs with other resource types using DataCite related identifier metadata.

For more information, see the Event Data Guide: [DataCite Event Data](doc:eventdata-guide)

## DataCite REST API

The DataCite REST API `/dois` endpoint can be used to query DOI metadata and relationships.

Citations and references are also summarized in the `relationships` section of the response. For example, one citation for 10.5061/dryad.qjq2bvqhq is summarized in <https://api.datacite.org/dois/10.5061/dryad.qjq2bvqhq>

```json
"relationships": {
  "client": {
    "data": {
    "id": "dryad.dryad",
    "type": "clients"
    }
  },
  "provider": {
    "data": {
    "id": "dryad",
    "type": "providers"
    }
  },
  "media": {
    "data": {
    "id": "10.5061/dryad.qjq2bvqhq",
    "type": "media"
    }
  },
  "references": {
    "data": []
  },
  "citations": {
    "data": [
    {
    "id": "10.1007/s10336-022-01988-z",
    "type": "dois"
    }
    ]
  },
  "parts": {
    "data": []
  },
  "partOf": {
    "data": []
  },
  "versions": {
    "data": []
  },
  "versionOf": {
    "data": []
  }
}
```

The “attributes” section  contains all core metadata—including relatedIdentifiers—as well as citation and reference counts. Here we can see the source of the citation—the relatedIdentifier with “IsCitedBy” relationType—and the citation count of 1:

```json
"relatedIdentifiers": [
  {
    "relationType": "IsCitedBy",
    "relatedIdentifier": "10.1007/s10336-022-01988-z",
    "relatedIdentifierType": "DOI"
  }
]
```

```json
"referenceCount": 0,
  "citationCount": 1,
  "citationsOverTime": [
    {
    "year": "2022",
    "total": 1
    }
	]
```

> 📘 Which types of events count as “citations” and “references”?
> 
> The citations and references sections of the `relationships` section summarize events from Event Data.
> 
> **Citations** include events where the given DOI (“A”) is the subject of a citation relationship or the object of a reference relationship:
> 
> - A is-cited-by B
> - A is-referenced-by B
> - A is-supplement-to B
> - B cites A
> - B references A
> - B is-supplemented-by A
> 
> **References** include events where the given DOI (“A”) is the subject of a reference relationship or the object of a citation relationship:
> 
> - B is-cited-by A
> - B is-referenced-by A
> - B is-supplement-to A
> - A cites B
> - A references B
> - A is-supplemented-by B
> 
> Only events between a DOI and a DOI are counted. (DOI-URL events are displayed in Event Data, but do not count towards citations and references.)

> 📘 What happens if I add more than one related identifier that produces a citation (or reference)?
> 
> When multiple relationTypes are used that have the same interpretation, they are not counted more than once.
> 
> For example, the following metadata would result in exactly one citation of DOI A by DOI B (10.5438/ExampleArticle):
> 
> DataCite DOI metadata for DOI A: 10.5438/ExampleDataset
> 
> ```
> <relatedIdentifier relatedIdentifierType="DOI" relationType="IsCitedBy">10.5438/ExampleArticle</relatedIdentifier>
> <relatedIdentifier relatedIdentifierType="DOI" relationType="IsReferencedBy">10.5438/ExampleArticle</relatedIdentifier>
> <relatedIdentifier relatedIdentifierType="DOI" relationType="IsSupplementTo">10.5438/ExampleArticle</relatedIdentifier>
> ```
> 
> Because all three relatedIdentifiers are for types of citations and point to the same object DOI, the citation is only counted once.

> 📘 What happens if I add a citation to a dataset’s DOI metadata, but the article also contains a reference to the dataset? Is the citation counted twice?
> 
> Connections created in both directions will not be counted twice.
> 
> For example, the following metadata would result in exactly one citation of DOI A (10.5438/ExampleDataset) by DOI B (10.5438/ExamplePreprint):
> 
> DataCite DOI metadata for DOI A: 10.5438/ExampleDataset
> 
> ```
> <relatedIdentifier relatedIdentifierType="DOI" relationType="IsCitedBy">10.5438/ExamplePreprint/relatedIdentifier>
> ```
> 
> DataCite DOI metadata for DOI B: 10.5438/ExamplePreprint
> 
> ```
> <relatedIdentifier relatedIdentifierType="DOI" relationType="Cites">10.5438/ExampleDataset/relatedIdentifier>
> ```

For more information, see the DataCite REST API Guide: [DataCite REST API Guide](doc:api) 

> 📘 
> 
> We are working hard to provide transparent information about data citation to our community and beyond. If you notice any errors or missing citations, please get in touch: [support@datacite.org](mailto:support@datacite.org)