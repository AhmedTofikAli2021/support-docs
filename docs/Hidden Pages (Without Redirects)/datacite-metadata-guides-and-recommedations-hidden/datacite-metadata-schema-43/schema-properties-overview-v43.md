---
title: DataCite Metadata Schema v4.3 Properties Overview
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
# Overview

The properties of the DataCite Metadata Schema are presented in this section. More detailed descriptions of the properties, and their related sub-properties, are provided in [DataCite Schema Mandatory Properties](doc:schema-mandatory-properties-v43) and [DataCite Schema Recommended and Optional Metadata](doc:schema-optional-properties-v43). 

There are three different levels of obligation for the metadata properties:

* **Mandatory (M)** properties must be provided,
* **Recommended (R)** properties are optional, but strongly recommended for interoperability 
* **Optional (O)** properties are optional and provide richer description. 

**Those clients who wish to enhance the prospects that their metadata will be found, cited and linked to original research are strongly encouraged to submit the Recommended as well as Mandatory set of properties.** Together, the Mandatory and Recommended set of properties and their sub-properties are especially valuable to information seekers and added-service providers, such as indexers. The Metadata Working Group members strongly urge the inclusion of metadata identified as Recommended for the purpose of achieving greater exposure for the resource’s metadata record, and therefore, the underlying research itself. 

The properties listed in [Table 1](#section-table-1-datacite-mandatory-properties) have the obligation level Mandatory, and *must* be supplied when submitting DataCite metadata. The properties listed in [Table 2](#section-table-2-datacite-recommended-and-optional-properties) have one of the obligation levels Recommended or Optional, and *may be* supplied when submitting DataCite metadata. 

The prospect that a resource's metadata will be found, cited and linked is enhanced by using the combined Mandatory and Recommended "super set" of properties and sub-properties. Those properties recommended by discovery are so indicated by a callout box like this:
 
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery",
  "body": "(Further notes about the property appear here, as necessary.)"
}
[/block]
Of the Recommended set of properties, the most important to use is the `Description` property, together with the Recommended sub-properties `descriptionType ="Abstract"` (see [DataCite Properties and property 17](#section-datacite-properties)). The detailed information about the [Description property](doc:schema-optional-properties-v41#section-17-description) includes descriptions of controlled list values, indicating those values that are especially important for information seekers and added-service providers. It cannot be emphasized enough how valuable an Abstract is to other scholars in finding the resource and then determining whether or not the resource, once found, is worth investigating further, re-using or validating.

## Table 1: DataCite Mandatory Properties
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "Property",
    "h-2": "Obligation",
    "0-0": "1",
    "1-0": "2",
    "2-0": "3",
    "3-0": "4",
    "4-0": "5",
    "5-0": "10",
    "0-1": "Identifier (with mandatory type sub-property)",
    "1-1": "Creator (with optional name identifier and affiliation sub-properties)",
    "2-1": "Title (with optional type sub-properties)",
    "3-1": "Publisher",
    "4-1": "PublicationYear",
    "5-1": "ResourceType (with mandatory general type description sub-property)",
    "0-2": "M",
    "1-2": "M",
    "2-2": "M",
    "3-2": "M",
    "4-2": "M",
    "5-2": "M",
    "h-3": "Recommended for discovery",
    "0-3": "yes",
    "1-3": "yes",
    "2-3": "yes",
    "3-3": "yes"
  },
  "cols": 3,
  "rows": 6
}
[/block]
## Table 2: DataCite Recommended and Optional Properties
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "Property",
    "h-2": "Obligation",
    "0-0": "6",
    "1-0": "7",
    "2-0": "8",
    "3-0": "9",
    "0-1": "Subject (with scheme sub-property)",
    "1-1": "Contributor (with type, name identifier, and affiliation sub-properties)",
    "2-1": "Date (with type sub-property)",
    "3-1": "Language",
    "4-0": "11",
    "5-0": "12",
    "6-0": "13",
    "7-0": "14",
    "8-0": "15",
    "9-0": "16",
    "4-1": "AlternateIdentifier (with type sub-property)",
    "5-1": "RelatedIdentifier (with type and relation type sub-properties)",
    "6-1": "Size",
    "7-1": "Format",
    "8-1": "Version",
    "9-1": "Rights",
    "10-0": "17",
    "11-0": "18",
    "0-2": "R",
    "1-2": "R",
    "2-2": "R",
    "3-2": "O",
    "4-2": "O",
    "5-2": "R",
    "6-2": "O",
    "7-2": "O",
    "8-2": "O",
    "9-2": "O",
    "10-1": "Description (with type sub-property)",
    "11-1": "GeoLocation (with point, box and polygon sub-properties)",
    "12-1": "FundingReference (with name, identifier, and award related sub-properties)",
    "12-0": "19",
    "10-2": "R",
    "11-2": "R",
    "12-2": "O"
  },
  "cols": 3,
  "rows": 13
}
[/block]
# Citation

Because many users of this schema are members of a variety of academic disciplines, DataCite remains discipline-agnostic concerning matters pertaining to academic style sheet requirements. Therefore, DataCite encourages rather than requires a particular citation format[(2)](#section-notes). In keeping with this approach, the following is the *preferred* format for rendering a DataCite citation for human readers using the mandatory properties of the schema:

> Creator (PublicationYear): Title. Publisher. Identifier 

It may also be desirable to include information from optional properties, such as Version. This is particularly important to include when citing software. For example: 

> Creator (PublicationYear): Title. Version. Publisher. (resourceTypeGeneral). Identifier

For citation purposes, DataCite prefers that DOI names are displayed as linkable, permanent URLs, for example, "https://doi.org/10.1234/abc"; however, the Identifier may appear in its original format. If the original format is chosen, be sure to include the characters “doi:" pre-pended to the Identifier as in “doi:10.1234/abc.” 

For resources that do not have a standard publication year value, DataCite suggests that PublicationYear should include the date that is preferred for use in a citation.

Here are several examples:
* Irino, T; Tada, R (2009): Chemical and mineral compositions of sediments from ODP Site 127-797. V. 2.1. Geological Institute, University of Tokyo. (dataset). http://doi.org/10.1594/PANGAEA.726855 
* Geofon operator (2009): GEFON event gfz2009kciu (NW Balkan Region). GeoForschungsZentrum Potsdam (GFZ). (dataset). http://doi.org/10.1594/GFZ.GEOFON.gfz2009kciu 
* Denhard, Michael (2009): dphase_mpeps: MicroPEPS LAF-Ensemble run by DWD for the MAP D-PHASE project. World Data Center for Climate. (dataset). http://doi.org/10.1594/WDCC/dphase_mpeps 

## A special note regarding citation of dynamic datasets

For datasets that are continuously and rapidly updated, there are special challenges both in citation and preservation. For citation, four approaches are possible:

>a) Cite a specific slice[(3)](#section-notes) or subset (the set of updates to the dataset made during a particular period of time or to a particular area of the dataset); Example: Data Request T.Jansen; SAHFOS; Work published 2014 via SAHFOS ; Area Def: 54-65°N, 0-45°W. Temporal Def: 1980-2012 (April-August) Taxonomic Def: All zooplankton; (dataset). https://doi.org/10.7487/2014.15.1.1

>b) Cite a specific snap-shot[(1)](#section-notes) (a copy of the entire dataset made at a specific time); Example: König-Langlo, G., & Sieger, R. (2010). BSRN snapshot 2010-01 as ISO image file (3.75 GB) [Data set]. PANGAEA - Data Publisher for Earth & Environmental Science. (dataset). https://doi.org/10.1594/pangaea.833424

>c) Cite the continuously updated dataset[(1)](#section-notes), but add an Access Date and Time to the citation. Example: Doe, J. and R. Roe. 2001. The FOO Data Set. Version 2.3. The FOO Data Center. (dataset). https://doi.org/10.xxxx/notfoo.547983. Accessed 1 May 2011.

>d) Cite a query[(4)](#section-notes), time-stamped for re-execution against a versioned database. The RDA recommended citation for this approach is: R. Roe. 2017. "The Moo Data Query" created at 2017-07-21 10:25:30 PID https://doi.org/10.xxxx/notmoo.857988. Subset of Moo Database (dataset). PID https://doi.org/10.xxxx/bigmoo.360873.


Notes:
The "slice," and "snap-shot" and "query" options require unique identifiers. Be aware that the third option (c) necessarily means that following the citation does not result in access to the resource as cited. This limits reproducibility of the work that uses this form of citation. In addition, please note that access date and time may be combined with the first (a), second (b) and fourth (d) options, but it must be used with the third option (c).

The fourth option (d) may shift more work onto repositories to store database versions for all the queries, so not all repositories will be able to support this alternative.

# DataCite Properties

The [DataCite Schema Mandatory Properties](doc:schema-mandatory-properties-v43) provides a detailed description of the mandatory properties, which *must* be supplied with any initial metadata submission to DataCite, together with their sub-properties. **If one of the required properties is unavailable** , please use one of the standard (machine-recognizable) codes listed in [Standard Values for Unknown Information](doc:schema-values-unknown-information-v43). In [DataCite Schema Recommended and Optional Properties](doc:schema-optional-properties-v43), the Recommended and Optional properties are described in detail. For an example of how to make a submission in XML format, please see the [XML Metadata Examples](doc:schema-metadata-examples-v43) or the [DataCite Metadata Schema website](http://schema.datacite.org/).  

Throughout this document, a naming convention has been used for all properties and sub-properties as follows: properties begin with a capital letter, whereas sub-properties begin with a lower case letter. If the name is a compound of more than one word, subsequent words begin with capital letters. This convention is known as “[camelCase](https://en.wikipedia.org/wiki/CamelCase).”

As indicated previously, this documentation uses a callout box to identify the combined Mandatory and Recommended "super set" of properties and sub-properties that enhance the prospect that the resource's metadata will be found, cited and linked.

The first column ("ID") indicates major properties by hierarchical number, and modifiers on those properties by lowercase letters. In the XML schema, the hierarchical numbers indicate elements of the schema, while lowercase letters indicate attributes of the related numbered element.

For each property, the Occurrence field indicates cardinality/quantity constraints for the properties as follows:

>0-n = optional and repeatable
>0-1 = optional, but not repeatable
>1-n = required and repeatable
>1 = required, but not repeatable

NOTE:
XML provides an xml:lang attribute that can be used on the properties `Title`, `Subject` and `Description`, and also on the properties `Creator`, `Contributor` and `Publisher` for organizational names. The allowed values are IETF BCP 47, ISO 639-1 language codes, e.g. en, de, fr. This provides a way to describe the language used for the content of the specified properties. The schema provides a `Language` property to be used to describe the language of the resource.

[block:api-header]
{
  "title": "XML Examples"
}
[/block]
Examples for various resource types and special cases can be found in [XML Metadata Examples](doc:schema-metadata-examples-v43).
[block:api-header]
{
  "type": "basic",
  "title": "XML Schema"
}
[/block]
The XML Schema is available here: http://schema.datacite.org/meta/kernel-4.3/metadata.xsd

Citation:

> DataCite Metadata Working Group. (2017). DataCite Metadata Schema for the Publication and Citation of Research Data. Version 4.1. DataCite e.V. http://doi.org/10.5438/0015

Note that the schema and the documentation will always have the same version number. 

Each subsequent version of the schema will be at the same location using an address composed in the same manner, that is: http://schema.datacite.org/meta/kernel-versionnumber/metadata.xsd. 

Earlier versions will continue to be available at their previous locations for backward compatibility.
[block:api-header]
{
  "title": "Notes"
}
[/block]
1. For more information on DCMI SAM, see http://wiki.dublincore.org/index.php/DCMI_Science_And_Metadata.
2.  In collaboration with CrossRef, DataCite has created a DOI Citation Formatter Service available at http://crosscite.org/citeproc/. The user can choose from more than 500 different citation formats in 45 different languages.
3. Ball, A. & Duke, M. (2015, July 30). ‘How to Cite Datasets and Link to Publications’. DCC How-to Guides. Edinburgh : Digital Curation Centre. Retrieved April 13, 2017, from: http://www.dcc.ac.uk/resources/how-guides/cite- datasets#sec:versions
4. Rauber, A., Uytvanck, D. V., Asmi, A., & Proll, S. (2016, February 09). Identification of Reproducible Subsets for Data Citation, Sharing and Re-Use. Retrieved April 13, 2017, from https://www.rd- alliance.org/system/files/documents/TCDL-RDA-Guidelines_160411.pdf
5. Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group. (2016) Software citation principles. PeerJ Computer Science 2:e86 https://doi.org/10.7717/peerj-cs.86