---
title: IGSN ID Metadata Recommendations
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
IGSN IDs are registered with metadata encoded in the DataCite Metadata Schema. The following guidance for IGSN ID metadata in the DataCite Metadata Schema was developed by the IGSN–DataCite Crosswalk and Metadata Management Working Group and sourced from the [IGSN–DataCite Crosswalk Recommendation](https://docs.google.com/document/d/16GTTvcnYvTDIYvypCq9dimNhDFK-fCipayO6YUngc90/edit). DataCite, the IGSN e.V., and the Working Group will continue to expand and refine metadata best practices for IGSN IDs over time.

## IGSN ID recommendations for mandatory properties in DataCite Metadata Schema

IGSN IDs must be registered with at least the six mandatory properties in the DataCite Metadata Schema.

### 1 Identifier

The `identifier` property will be automatically populated with a DOI upon the creation of an IGSN ID. The system will assign a random DOI suffix unless a specific suffix is supplied using Fabrica or DataCite APIs.

### 2 Creator

The `creator` property contains a list of “the main researcher(s) involved...in priority order.” For IGSN IDs, this could be the sample collector/creator, chief scientist, curator, or even the person who deposited the sample into a repository.

As a norm, IGSN ID registrants are expected to collect information about the sample owner, Principle Investigator, and/or otherwise. However, if no appropriate name is available, the property will be populated with the name of the IGSN ID Repository registrant or an appropriate standard value for unknown information from [Appendix 3: Standard values for unknown information](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-3/).

### 3 Title

The `title` property should include appropriate elements that would help find and distinguish a sample. The exact syntax is at the discretion of the IGSN ID registrant. Appropriate elements might include:

- The basic form of the object that is registered. For example, polished section, core, pulp, solution, dredge haul in a box, lot, or piece of material.
- The material or materials that compose the sample. For example, water, granite, or tissue.
- Local sample identifiers. 

We strongly recommend populating the `title` property with an appropriate value to enhance discoverability. If no title information is available, there is the option to fill this property with an appropriate standard value for unknown information from [Appendix 3: Standard values for unknown information](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-3/).

### 4 Publisher

The `publisher` property contains “the name of the entity that holds, archives, publishes prints, distributes, releases, issues, or produces the resource.” For IGSN IDs, this should be the organization registering the IGSN ID for the physical sample.

### 5 PublicationYear

The `publicationYear` property should contain the year when the sample was first made available to the research community. This is likely to be the year at the time the physical sample is registered unless the sample was released before registration of its metadata record.

The DataCite Metadata Schema provides the following additional guidance for the `publicationYear` property that is relevant to material samples:

- If the date of public availability cannot be determined, use the date of registration.
- If an embargo period has been in effect, use the date when the embargo period ends.
- If there is no standard publication year value, use the date that would be preferred from a citation perspective.

### 10 ResourceType

The `resourceType` property may be populated with resource types from external ontologies or shared vocabularies. In the absence of an agreed vocabulary, the use of the terms “material sample” or “‘feature-of-interest” are strongly recommended to at least distinguish between these sampling concepts. A material sample is a specialization of a larger feature-of-interest, which is typically the collection site. For example, in the Geosciences, a feature-of-interest might be a lake, tree, cross-section, transect, or borehole. 

### 10.a resourceTypeGeneral

The `resourceTypeGeneral` property is “PhysicalObject” for all IGSN IDs.

## IGSN ID recommendations for other properties in DataCite Metadata Schema

### 6 Subject

The free-text `subject` property contains the "subject, keyword, classification code, or key phrase describing the resource." For IGSN IDs, this is the materials that compose the sample. Since materials may be categorized under different schemata, the sub-properties `subjectScheme` and `schemeURI` should also be included whenever possible.

### 7 Contributor

All institutions and people involved in a sample’s workflow—from collection to archival (or discarding/destruction)—may be captured in the free-text `contributor` property. If `contributor` is used, the sub-properties `contributorName` and `contributorType` are mandatory. 

Note that to be included in the reference to a resource, a person or organization must be listed in a `creator` property (and can then be additionally listed in a `contributor` property). People and organizations listed only in a `contributor` property are not included in the resource reference.

### 8 Date

The `date` property may be used to log events relevant to the physical object. The `date` property requires the `dateType` sub-property, which must be entered from a controlled list. The "Collected" `dateType` may be used to record when a sample was collected. At this time, there is no controlled list value for “Destroyed”, which may be pertinent to your material samples metadata. Pending the potential addition of an equivalent value, we advise using a `date` property with `dateType` “Other” and “Destroyed” in the `dateInformation` field.

### 11 AlternateIdentifier

The `alternateIdentifier` property may be used to enter any other identifiers for the material sample, including local sample identifiers. For alternate identifiers that were assigned by a researcher or within a project, “local” is the default recommended alternateIdentifierType.

### 12 RelatedIdentifier

Connecting samples to one another, and to research based on them, is a primary goal of the IGSN ID. Such connections are captured through  `relatedIdentifier` properties, which list the globally unique Identifiers assigned to related resources. It is therefore recommended that `relatedIdentifier` is used to the maximum extent possible and is updated on a regular basis.

The mandatory `relationType` sub-property describes relationships between the material sample for which the IGSN ID is being registered and related resources (features-of-interest, parent samples, subsamples, datasets, publications, etc.).

The `relatedIdentifier` property can be used to make connections that mirror sample hierarchies. Because the parent IGSN ID is a key element in IGSN ID metadata, it is recommended that a child (sub)sample identifies its parent using the `relationType` "IsPartOf" or "IsDerivedFrom". Vice versa, a parent sample can identify its children using "HasPart" or "IsSourceOf". Of these four `relationTypes`, only "IsPartOf" and "HasPart" currently create Event Data visible in the REST API and GraphQL API. See [Connecting to Works](doc:connecting-to-works). 

Relationships to other IGSN IDs registered with DataCite services should use `relatedIdentifierType` `DOI`. 

### 17 Description

It is valuable to include additional information about a sample, particularly about its "birth," in the free-text `description` property. If the `description` property is used, then the sub-property `descriptionType` is mandatory. Values for the latter are selected from a controlled list, with the most relevant for IGSN IDs being:

- Abstract – Brief description of the resource and the context in which it was created.
- Methods – The methodology employed for the study or research. For IGSN IDs, this is the collection method.

Both of these are important for discovery purposes.

### 18 GeoLocation

The `geoLocation` property is used to encode information on the "spatial region or named place where the data was gathered or about which the data is focused." The property can be repeated to indicate a number of different locations, and can express a location as a point, bounding box, or polygon, or simply as a free-text description through its (respective) sub-properties: `geoLocationPoint`, `geoLocationBox`, `geoLocationPolygon`, and `geoLocationPlace`.

For IGSN IDs, this property will contain where a sample was acquired relative to the Earth or another astronomical object. Note that it may not be relevant for samples that are ‘non-geographic’ (e.g., a synthetic material).

## Example DataCite metadata following IGSN ID recommendations

### DataCite XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<resource
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns="http://datacite.org/schema/kernel-4" xsi:schemaLocation="http://datacite.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4/metadata.xsd">
    <identifier identifierType="DOI">10.21384/SP0001</identifier>
    <creators>
        <creator>
            <creatorName nameType="Personal">Miller, Elizabeth</creatorName>
            <givenName>Elizabeth</givenName>
            <familyName>Miller</familyName>
            <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="https://orcid.org">https://orcid.org/0000-0001-5000-0007</nameIdentifier>
        </creator>
    </creators>
    <titles>
        <title>PL04, Lapilli tuff, Rock</title>
    </titles>
    <publisher>Institute of Materials Science</publisher>
    <publicationYear>2022</publicationYear>
    <resourceType resourceTypeGeneral="PhysicalObject">Material sample</resourceType>
    <subjects>
        <subject subjectScheme="iSamples Material Sample Type Vocabulary" schemeURI="https://w3id.org/isample/vocabulary/specimentype/0.9">Physical specimen</subject>
    </subjects>
    <contributors>
        <contributor contributorType="HostingInstitution">
            <contributorName nameType="Organizational">DataCite</contributorName>
            <nameIdentifier nameIdentifierScheme="ROR" schemeURI="https://ror.org">https://ror.org/04wxnsj81</nameIdentifier>
        </contributor>
    </contributors>
    <dates>
        <date dateType="Collected">2022-06-01</date>
        <date dateType="Other" dateInformation="Destroyed">2022-06-15</date>
        <date dateType="Issued">2022</date>
    </dates>
    <relatedIdentifiers>
        <relatedIdentifier relatedIdentifierType="DOI" relationType="IsPartOf" resourceTypeGeneral="PhysicalObject">10.21384/sp0002</relatedIdentifier>
        <relatedIdentifier relatedIdentifierType="DOI" relationType="IsReferencedBy" resourceTypeGeneral="Dataset">10.26022/ieda/112166</relatedIdentifier>
        <relatedIdentifier relatedIdentifierType="URL" relationType="HasMetadata">https://data.datacite.org/application/citeproc+json/10.5072/example-full</relatedIdentifier>
    </relatedIdentifiers>
    <sizes/>
    <formats/>
    <version/>
    <descriptions>
        <description xml:lang="en" descriptionType="Abstract">Poorly sorted volcaniclastic deposit.</description>
        <description xml:lang="en" descriptionType="Methods">Collected using rock corer.</description>
    </descriptions>
    <geoLocations>
        <geoLocation>
            <geoLocationPlace>Gulf of California</geoLocationPlace>
            <geoLocationPoint>
                <pointLongitude>-67.302</pointLongitude>
                <pointLatitude>31.233</pointLatitude>
            </geoLocationPoint>
            <geoLocationBox>
                <westBoundLongitude>-71.032</westBoundLongitude>
                <eastBoundLongitude>-68.211</eastBoundLongitude>
                <southBoundLatitude>41.090</southBoundLatitude>
                <northBoundLatitude>42.893</northBoundLatitude>
            </geoLocationBox>
            <geoLocationPolygon>
                <polygonPoint>
                    <pointLatitude>41.991</pointLatitude>
                    <pointLongitude>-71.032</pointLongitude>
                </polygonPoint>
                <polygonPoint>
                    <pointLatitude>42.893</pointLatitude>
                    <pointLongitude>-69.622</pointLongitude>
                </polygonPoint>
                <polygonPoint>
                    <pointLatitude>41.991</pointLatitude>
                    <pointLongitude>-68.211</pointLongitude>
                </polygonPoint>
                <polygonPoint>
                    <pointLatitude>41.090</pointLatitude>
                    <pointLongitude>-69.622</pointLongitude>
                </polygonPoint>
                <polygonPoint>
                    <pointLatitude>41.991</pointLatitude>
                    <pointLongitude>-71.032</pointLongitude>
                </polygonPoint>
            </geoLocationPolygon>
        </geoLocation>
    </geoLocations>
</resource>
```

### DataCite JSON

```json
{
  "id": "https://doi.org/10.21384/sp0001",
  "doi": "10.21384/SP0001",
  "url": "https://app.geosamples.org/sample/igsn/3210000DH&header=1",
  "types": {
    "ris": "GEN",
    "bibtex": "misc",
    "citeproc": "article",
    "schemaOrg": "CreativeWork",
    "resourceType": "Material sample",
    "resourceTypeGeneral": "PhysicalObject"
  },
  "creators": [
    {
      "name": "Miller, Elizabeth",
      "nameType": "Personal",
      "givenName": "Elizabeth",
      "familyName": "Miller",
      "nameIdentifiers": [
        {
          "schemeUri": "https://orcid.org",
          "nameIdentifier": "https://orcid.org/0000-0001-5000-0007",
          "nameIdentifierScheme": "ORCID"
        }
      ]
    }
  ],
  "titles": [
    {
      "title": "PL04, Lapilli tuff, Rock"
    }
  ],
  "publisher": "Institute of Materials Science",
  "container": {
    "type": "Series",
    "identifier": "10.82206/sp0002",
    "identifierType": "DOI"
  },
  "subjects": [
    {
      "subject": "Physical specimen",
      "schemeUri": "https://w3id.org/isample/vocabulary/specimentype/0.9",
      "subjectScheme": "iSamples Material Sample Type Vocabulary"
    }
  ],
  "contributors": [
    {
      "name": "DataCite",
      "nameType": "Organizational",
      "affiliation": [],
      "contributorType": "HostingInstitution",
      "nameIdentifiers": [
        {
          "schemeUri": "https://ror.org",
          "nameIdentifier": "https://ror.org/04wxnsj81",
          "nameIdentifierScheme": "ROR"
        }
      ]
    }
  ],
  "dates": [
    {
      "date": "2022-06-01",
      "dateType": "Collected"
    },
    {
      "date": "2022-06-15",
      "dateType": "Other",
      "dateInformation": "Destroyed"
    },
    {
      "date": "2022",
      "dateType": "Issued"
    }
  ],
  "publicationYear": 2022,
  "identifiers": [],
  "sizes": [],
  "formats": [],
  "rightsList": [],
  "descriptions": [
    {
      "lang": "en",
      "description": "Poorly sorted volcaniclastic deposit.",
      "descriptionType": "Abstract"
    },
    {
      "lang": "en",
      "description": "Collected using rock corer.",
      "descriptionType": "Methods"
    }
  ],
  "geoLocations": [
    {
      "geoLocationBox": {
        "eastBoundLongitude": "-68.211",
        "northBoundLatitude": "42.893",
        "southBoundLatitude": "41.090",
        "westBoundLongitude": "-71.032"
      },
      "geoLocationPlace": "Gulf of California",
      "geoLocationPoint": {
        "pointLatitude": "31.233",
        "pointLongitude": "-67.302"
      },
      "geoLocationPolygon": [
        {
          "polygonPoint": {
            "pointLatitude": "41.991",
            "pointLongitude": "-71.032"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "42.893",
            "pointLongitude": "-69.622"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "41.991",
            "pointLongitude": "-68.211"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "41.090",
            "pointLongitude": "-69.622"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "41.991",
            "pointLongitude": "-71.032"
          }
        }
      ]
    }
  ],
  "fundingReferences": [],
  "relatedIdentifiers": [
    {
      "relationType": "IsPartOf",
      "relatedIdentifier": "10.21384/sp0002",
      "resourceTypeGeneral": "PhysicalObject",
      "relatedIdentifierType": "DOI"
    },
    {
      "relationType": "IsReferencedBy",
      "relatedIdentifier": "10.26022/ieda/112166",
      "resourceTypeGeneral": "Dataset",
      "relatedIdentifierType": "DOI"
    },
    {
      "relationType": "HasMetadata",
      "relatedIdentifier": "https://data.datacite.org/application/citeproc+json/10.5072/example-full",
      "relatedIdentifierType": "URL"
    }
  ],
  "relatedItems": [],
  "schemaVersion": "http://datacite.org/schema/kernel-4",
  "providerId": "datacite",
  "clientId": "datacite.qyacaz",
  "agency": "datacite",
  "state": "registered"
}
```