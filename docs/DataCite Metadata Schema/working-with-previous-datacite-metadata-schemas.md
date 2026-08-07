---
title: Working with Previous DataCite Metadata Schemas
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
[block:api-header]
{
  "title": "Current Version"
}
[/block]
The current version of the DataCite Metadata Schema is 4.3. The official version of the DataCite Metadata Schema, as well as the official version of the schema documentation in PDF format, can always be found at the [DataCite Metadata Schema website](https://schema.datacite.org). For convenience purposes, a copy of the schema documentation can also be found in support pages under [DataCite Metadata Schema 4.3](doc:datacite-metadata-schema-43). 

The most recent version of the DataCite Metadata Schema is the preferred version of the schema for [DOI Fabrica](https://doi.datacite.org) and our [APIs](doc:apis), but many of the previous versions of the DataCite Metadata Schema are still valid.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/021f106-Screen_Shot_2017-01-02_at_10.41.30.png",
        "Screen Shot 2017-01-02 at 10.41.30.png",
        1632,
        1176,
        "#329174"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Other Supported Versions"
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Retirement of Schema Versions 2.x",
  "body": "Beginning 1 January 2019, it will no longer be possible to register new DOIs using either DataCite Metadata Schema 2.1 or 2.2. \n\nTo register DOIs using a more recent version of the Schema, it is necessary to update the namespace submitted as part of the metadata, e.g. `xmlns=\"http://datacite.org/schema/kernel-4\"`. \n\nPlease review the documentation for your selected replacement Schema version to learn more about the available metadata requirements and options. In particular, please note that resourceTypeGeneral is a required field as of Schema 4.0."
}
[/block]
* DataCite Metadata Schema 4.2 (Released Released 20 March 2019)
  * Documentation Version 4.2 https://doi.org/10.5438/bmjt-bx77
  * Schema Version 4.2 http://doi.org/10.5438/rv0g-av03
  * [Examples](https://schema.datacite.org/meta/kernel-4.2/)
* DataCite Metadata Schema 4.1 (Released Released 23 Oct 2017)
  * Documentation Version 4.1 http://doi.org/10.5438/0014
  * Schema Version 4.1 http://doi.org/10.5438/0015
  * [Examples](https://schema.datacite.org/meta/kernel-4.1/)
* DataCite Metadata Schema 4.0 (Released 19 Sep 2016)
  * Documentation Version 4.0 http://doi.org/10.5438/0012
  * Schema Version 4.0 http://doi.org/10.5438/0013
  * [Examples](http://schema.datacite.org/meta/kernel-4.0/)
* DataCite Metadata Schema 3.1 (Released 16 Oct 2014)
  * Documentation Version 3.1 https://doi.org/10.5438/0010
  * Schema Version 3.1 https://doi.org/10.5438/0011
  * [Examples](http://schema.datacite.org/meta/kernel-3.1/)
* DataCite Metadata Schema 3.0 (Released 24 Jul 2013)
  * Documentation Version 3.0 https://doi.org/10.5438/0008
  * Schema Version 3.- https://doi.org/10.5438/0009
  * [Examples](http://schema.datacite.org/meta/kernel-3.0/)
[block:api-header]
{
  "type": "basic",
  "title": "Obsolete Versions (no longer supported)"
}
[/block]
* DataCite Metadata Schema 2.2 (Released 1 Jul 2011)
  * Documentation Version 2.2 https://doi.org/10.5438/0005
  * Schema Version 2.2 https://doi.org/10.5438/0006
  * [Examples](http://schema.datacite.org/archive/kernel-2.2/)
* DataCite Metadata Schema 2.1 (Released 28 Mar 2011)
  * Documentation Version 2.1 https://doi.org/10.5438/0003
  * Schema Version 2.1 https://doi.org/10.5438/0004
  * [Example](http://schema.datacite.org/archive/kernel-2.1/)
* DataCite Metadata Schema 2.0 (24 Jan 2011)
  * Documentation Version 2.0 https://doi.org/10.5438/0001
  * Schema Version 2.0 https://doi.org/10.5438/0002
[block:api-header]
{
  "type": "basic",
  "title": "Naming Convention"
}
[/block]
Starting with version 3.0 only major releases will have a new namespace, meaning that it is only necessary to specify `http://datacite.org/schema/kernel-3` rather than `http://datacite.org/schema/kernel-3.1`, for example.

The version number is formatted as: Major.Minor

* Major Version — A major release is for adding features that require breaking backward compatibility with previous versions or represent fundamental changes. For a major release, the MAJOR component is incremented by one and the MINOR component is set to zero, e.g. 3.1 to 4.0.
* Minor Version — A minor release is for adding features that do not break backward compatibility with previous versions and for fixing bugs that may or may not break backwards compatibility. For a minor release, the MINOR component is incremented by one, e.g. 3.0 to 3.1.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]