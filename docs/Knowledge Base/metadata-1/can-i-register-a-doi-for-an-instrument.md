---
title: Can I register a DOI for an instrument?
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
As of DataCite Metadata Schema 4.5, “Instrument” is included in the resourceTypeGeneral controlled list values. An instrument is defined as “A device, tool or apparatus used to obtain, measure and/or analyze data”.

The value is part of property 10.a resourceTypeGeneral, and can also be used in other places where resourceTypeGeneral is used (e.g., as part of the relatedIdentifiers metadata in property 12.f resourceTypeGeneral, or as part of the relatedItem metadata in 20.a relatedItemType). 

You can already use this value when registering a DOI in [DataCite Fabrica](doc:doi-fabrica) or via the [REST API](doc:api), so if your organization is a DataCite member or part of a consortium you can get started with registering DOIs for instruments!

The schema also includes a relationType pair: `IsCollectedBy` - which may be used to indicate the relationship between a dataset and an instrument that is used to collect, measure, obtain, or observe data (as in, dataset A is IsCollectedBy instrument B) and `Collects` - which may be used to indicate the relationship between an instrument and where it has been used to collect, measure, obtain, or observe data (as in, instrument A collects dataset B)

Please see the relevant sections of the DataCite Metadata Schema documentation below:

- [Schema 4.5 Version Update: Support for Instruments](https://datacite-metadata-schema.readthedocs.io/en/4.5/introduction/version-update/#support-for-instruments)
- [resourceTypeGeneral Controlled Vocabulary](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/resourceTypeGeneral/#instrument)

The [FAIR Facilities and Instruments](https://ncar.github.io/FAIR-Facilities-Instruments/) project also provides further guidance and recommendations, as follows:

- Recommendations:
  - [Recommendations Toward a Framework for Adoption and Use of Persistent Identifiers for Research Facilities, Platforms, and Instruments](https://doi.org/10.5281/zenodo.18436644), February 2026.
- Articles:
  - Mayernik, Matthew, Andrew Johnson, Renaine Julian, Matthew Murray, Claudius Mundoma, Aditya Ranganath, and Greg Stossmeister. “[Persistent Identifiers for Instruments and Facilities: Current State, Challenges, and Opportunities](https://doi.org/10.7191/jeslib.964).” Journal of eScience Librarianship 13 (3): e964. 2024-12-03.
  - Mayernik, Matthew, Johnson, Andrew, Julian, Retanine, Mundoma, Claudius, Murray, Matthew, and Ranganath, Aditya. “[Persistent Identification of Facilities and Instruments within Scholarly Infrastructure](https://doi.org/10.1002/pra2.1476).” Proceedings of the Association for Information Science and Technology, 62: 1587-1589. 2025-10.