---
title: DataCite DOIs for Instruments
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
The [DataCite Metadata Schema](https://schema.datacite.org/) defines an instrument as “A device, tool or apparatus used to obtain, measure and/or analyze data”.  The resourceTypeGeneral value “Instrument” can be used when assigning DOIs to instruments.

The schema also includes a [relationType](https://datacite-metadata-schema.readthedocs.io/en/4.7/appendices/appendix-1/relationType/) pair for relationships between instrument and data: IsCollectedBy and Collects. These relationTypes can be applied through the [RelatedIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/) and [RelatedItem](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relateditem/) properties, which facilitate connections between resources.

> 📘 
> 
> `IsCollectedBy` may be used to indicate the relationship between a dataset and an instrument that is used to collect, measure, obtain, or observe data (as in, dataset A is IsCollectedBy instrument B).
> 
> `Collects` may be used to indicate the relationship between an instrument and where it has been used to collect, measure, obtain, or observe data (as in, instrument A collects dataset B).

Please see the relevant sections of the DataCite Metadata Schema documentation below:

- DataCite Metadata Schema: [PIDINST Schema Mapping](https://datacite-metadata-schema.readthedocs.io/en/4/mappings/pidinst/)
- resourceTypeGeneral Controlled Vocabulary: [Instrument](https://datacite-metadata-schema.readthedocs.io/en/4.7/appendices/appendix-1/resourceTypeGeneral/#instrument)

### Real metadata example for an instrument

[E3 - Residual Stress Analysis and Texture Diffractometer](https://doi.org/10.5442/ni000008):  
DataCite Commons record: <https://commons.datacite.org/doi.org/10.5442/ni000008>

```xml
<resource xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://datacite.org/schema/kernel-4" xsi:schemaLocation="http://datacite.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4.3/metadata.xsd">
  <identifier identifierType="DOI">10.5442/NI000008</identifier>
  <creators>
    <creator>
      <creatorName nameType="Organizational">Helmholtz-Zentrum Berlin für Materialien und Energie</creatorName>
      <nameIdentifier nameIdentifierScheme="ROR" schemeURI="https://ror.org/">02aj13c28</nameIdentifier>
    </creator>
  </creators>
  <titles>
    <title titleType="Other">E3 - Residual Stress Analysis and Texture Diffractometer</title>
  </titles>
  <publisher>Helmholtz-Zentrum Berlin für Materialien und Energie</publisher>
  <publicationYear>2019</publicationYear>
  <subjects>
    <subject>Neutron source</subject>
    <subject>BER II</subject>
    <subject>Stress and Strain/Textures</subject>
  </subjects>
  <contributors>
    <contributor contributorType="HostingInstitution">
      <contributorName nameType="Organizational">Helmholtz-Zentrum Berlin für Materialien und Energie</contributorName>
      <nameIdentifier nameIdentifierScheme="ROR" schemeURI="https://ror.org/">02aj13c28</nameIdentifier>
    </contributor>
  </contributors>
  <resourceType resourceTypeGeneral="Instrument">BER II Beamline</resourceType>
  <relatedIdentifiers>
    <relatedIdentifier relatedIdentifierType="DOI" relationType="IsDescribedBy">10.17815/jlsrf-2-126</relatedIdentifier>
  </relatedIdentifiers>
  <descriptions>
    <description descriptionType="Abstract">
      The diffractometer is designed for strain and stress analysis for simple geometric samples as well as for industrial applications and heavy components of arbitrary shape. The diffractometer itself consists of two big omega circles (Ω and 2Θ) with a diameter of 800 mm and upon a translation table (xyz-direction) for sample positioning in vertical and horizontal direction. This set up is installed for handling heavy and/or large samples and components such as impellers or turbines with diameters of up to half a meter and loads up to 300 kg. A range of equipment for sample positioning is available, such as a closed Eulerian cradle for samples with weights of up to 5 kg. A second cradle for heavy samples (up to 50 kg) with the ability to tilt the samples up to 90° is used to measure three perpendicular sample orientations. Gauge volumes can be adjusted horizontally and vertically by a computer-controlled variable primary slit in a range from 0-10 mm and 0-20 mm respectively. Rapid data visualization as well as evaluation is performed by the specially designed software SteCa.
    </description>
  </descriptions>
</resource>
```

For more metadata examples, please refer to the following guidance from the PID4NFDI project:

- Metadata Examples for Instrument PIDs: Guidance Document  <https://doi.org/10.5281/zenodo.17535688>
- Linking Instrument PIDs With Related Research Entities: [Guidance Document](https://doi.org/10.5281/zenodo.17535289) 
- DOIs for Instruments at the Helmholtz-Zentrum Berlin: [Use Case Analysis](https://doi.org/10.5281/zenodo.17726735) 
- [PID4NFDI resources](https://pid.services.base4nfdi.de/services/instruments/)

The FAIR Facilities and Instruments project also provides further guidance and recommendations, as follows:

Recommendations:

- [Recommendations Toward a Framework for Adoption and Use of Persistent Identifiers for Research Facilities, Platforms, and Instruments](https://doi.org/10.5281/zenodo.18436644), February 2026.

Articles:

- Mayernik, Matthew, Andrew Johnson, Renaine Julian, Matthew Murray, Claudius Mundoma, Aditya Ranganath, and Greg Stossmeister. “[Persistent Identifiers for Instruments and Facilities: Current State, Challenges, and Opportunities.](https://doi.org/10.7191/jeslib.964)” Journal of eScience Librarianship 13 (3): e964. 2024-12-03.
- Mayernik, Matthew, Johnson, Andrew, Julian, Retanine, Mundoma, Claudius, Murray, Matthew, and Ranganath, Aditya. “[Persistent Identification of Facilities and Instruments within Scholarly Infrastructure.](https://doi.org/10.1002/pra2.1476)” Proceedings of the Association for Information Science and Technology, 62: 1587-1589. 2025-10.