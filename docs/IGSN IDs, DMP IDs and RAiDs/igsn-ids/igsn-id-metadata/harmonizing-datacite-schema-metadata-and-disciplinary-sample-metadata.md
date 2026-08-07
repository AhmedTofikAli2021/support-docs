---
title: Harmonizing DataCite Schema Metadata and Disciplinary Sample Metadata
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
Through a [partnership](https://doi.org/10.5438/7z70-1155) between DataCite and IGSN e.V., [International Generic Sample Numbers](doc:igsn-ids) (IGSN IDs) are functionally [Digital Object Identifiers](doc:doi-basics) (DOIs) with metadata structured according to the DataCite Metadata Schema. Here we clarify the differences in terms of metadata and discoverability between the generalized [DataCite Metadata Schema](https://schema.datacite.org/) and sample-specific schemas that typically offer greater flexibility/extensibility and richness of information than the DataCite Metadata Schema.

## DataCite Metadata Schema & IGSN IDs

Discovery of material sample metadata occurs across layers, from the persistent identifier (PID) layer through to the catalog/repository layer that contains sample metadata particular to an institution, community, and/or discipline. Each of these layers addresses a different use case:

- PID metadata address primary citation and core discovery of a material sample.
- Catalog/repository metadata ("catalog metadata" hereon) address domain-specific discovery and reuse of a material sample.

The DataCite Metadata Schema is deliberately generic, with a [core list of properties](https://datacite-metadata-schema.readthedocs.io/en/4/properties/) that enable accurate and consistent identification of any material sample registered with an IGSN ID. **It is not intended to supplant a catalog metadata schema** that fully describes a material sample; rather, the DataCite Metadata Schema works alongside the catalog metadata schema.

At a basic level, the DataCite Metadata Schema fosters general findability and accessibility of a material sample, attribution of the sample’s "creators", and [connectivity](doc:making-and-using-connection-metadata) of the sample to other related entities ([works](doc:connecting-to-works), [people](doc:connecting-to-people), and [organizations](doc:connecting-to-organizations)) associated with PIDs. In addition, material samples registered with an IGSN ID will be often described using catalog metadata that are beyond the DataCite Metadata Schema. These catalog metadata enable enhanced discoverability and distinction of the material sample, provide advanced knowledge on how the sample may be interoperated with other research outputs, and inform about how it may be used or repurposed in (multi)disciplinary contexts.

The catalog metadata used to richly describe a material sample registered with an IGSN ID can, and should, be captured to the greatest extent within the PID metadata and [landing page](doc:considerations-when-setting-up-an-igsn-repository-and-registration-workflow#landing-pages). To ensure this, the IGSN–DataCite partnership has produced metadata [guidance](doc:igsn-id-metadata-recommendations) and [best practices](doc:enriching-igsn-id-metadata-in-the-datacite-metadata-schema) for IGSN IDs, and the partnership is continuing over time to expand and refine these recommendations. Best practices include the direct linking to a catalog metadata schema from a sample’s PID metadata record through [`relatedIdentifer`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/) metadata in the DataCite Metadata Schema. It is also possible to directly expose both PID and catalog metadata when resolving an IGSN ID using existing technologies, such as content negotiation and the [DataCite Content Negotiation service](doc:datacite-content-resolver).

## `relatedIdentifier` Metadata

The DataCite Metadata Schema is not designed to capture all of a material sample’s catalog metadata. However, the DataCite Metadata Schema has a provision to link to the catalog metadata schema such that someone discovering the sample through its IGSN ID can access all of its available information.

The DataCite Metadata Schema [`relatedIdentifer`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/) metadata property with the subproperty [`relationType`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#b-relationtype) = “[`HasMetadata`](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/relationType/#hasmetadata)” can be used to connect a DataCite metadata record to the catalog metadata schema used to describe a material sample. Commonly, a material sample’s catalog metadata schema is shared via a webpage, and in this case, the `relatedIdentifierType` subproperty of `relatedIdentifer` is set to “[URL](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/relatedIdentifierType/#url)”. Other `relatedIdentifer` subproperties when `relationType` = `HasMetadata` are [`relatedMetadataScheme`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#c-relatedmetadatascheme), [`schemeURI`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#d-schemeuri), and [`schemeType`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#e-schemetype).

### Example of `HasMetadata`

```Text XML
…  
     <resourceType resourceTypeGeneral="PhysicalObject"> Material Sample</resourceType>  
…  
    <relatedIdentifiers>  
        <relatedIdentifier relatedIdentifierType="URL" relatedMetadataScheme="Darwin Core Archive" relationType="HasMetadata" schemeType="DwC-A" schemeURI="http://rs.tdwg.org/dwc/terms/guides/text/index.htm"><https://glis.fao.org/glisapi/v1/pgrfas?_format=dwc&doi=10.18730/SSDPA></relatedIdentifier>  
    </relatedIdentifiers>  
…
```

## DataCite Content Negotiation

The DataCite Content Negotiation service is available at <https://data.crosscite.org/>. When requests are made to doi.org with a [supported content type](doc:datacite-content-resolver#supported-content-types), the DataCite Content Negotiation service will return the PID metadata of the IGSN ID in the specified format rather than redirecting the request to its landing page URL. 

Requests for unsupported formats are redirected to the landing page URL. Catalog metadata may be returned if the landing page URL supports content negotiation and the specified content type. Requests can also be made directly to the landing page URL with any content type.

Learn more about the [DataCite Content Negotiation service](doc:datacite-content-resolver).