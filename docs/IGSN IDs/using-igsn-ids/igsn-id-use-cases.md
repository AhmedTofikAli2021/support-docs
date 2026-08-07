---
title: IGSN ID Use Cases
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
## General Information on Usage of IGSN IDs

IGSN IDs may be registered for all material samples from any research domain. In addition to individual samples, IGSN IDs may also be assigned to: 

- **Collections or aggregations of samples**. You may not want to have a PID for every object within a collection. If a whole aggregate is usually referenced, it can be registered with an IGSN ID. Additional IGSN IDs may then be registered for specific samples within the collection as necessary. Such samples are children of the parent collection and may be connected in the metadata using [`relatedIdentifers`](https://support.datacite.org/docs/connecting-to-works).
- **Features-of-interest**. A material sample is a specialization of a ‘feature-of-interest’ upon which the sampling activity was carried out; namely, the collection site (such a site may not exist for samples that are synthesized in a laboratory). Similar to collections, samples in this case are children of their parent feature-of-interest.
- **Ephemeral samples**. Non-persistent material samples may be registered with IGSN IDs. It is common for samples to be destroyed during an analytical process or discarded after testing; they may also degrade over time. For synthesized samples, they may exist only at a certain point during the experimental process before disappearing again. In all cases, the sample metadata should provide clear information on the current status of the sample.

## Specific Use Cases for IGSN IDs

Below is an outline of the five main IGSN ID use cases. Within these use cases is information about developing landing pages for material samples registered with IGSN IDs, labelling material samples with IGSN IDs, incorporating IGSN IDs into the material sample workflow, creating relationships among IGSN IDs, and connecting IGSN IDs to other resources that are registered with PIDs. 

### Linking to the Web – Open Science

Registering an IGSN ID for a material sample links the physical to the digital world, creating a long-term digital footprint that may outlast the sample itself. It provides evidence that the sample exists, as well as preserving information that helps ensure past investment is not lost and supports potential future research. This is especially important for rare or unique samples.

The digital representation of a material sample is its [landing page](https://support.datacite.org/docs/landing-pages), which displays a description of the sample identified by the IGSN ID. The presentation of metadata on landing pages often differs among portals, but it should include as many elements as possible that improve the discoverability and distinction of each sample. For example: sample images, maps of sample locations, relationships to other samples, associated data, publications, organizations/people.

Metadata may also be withheld on landing pages and in DataCite services to protect sensitive information and embargoed information, such as sites/samples that are vulnerable, have indigenous significance, or are subject to commercial interests. It is recommended that when such information is excluded, whether temporarily or permanently, the full sample metadata schema used by the facility is linked to the IGSN ID metadata record and/or landing page in order to make transparent all the types of information that are collected. In addition, a note might be included on landing pages stating (what) information is being withheld, any conditions to access that information, and who to contact.

### Locating – Collection Management

Knowledge on samples has traditionally been with the Principal Investigators (PIs) leading a project, with a lack of common, standardized infrastructure for fieldwork and sample management. This means that such knowledge may disappear if a PI is no longer at a facility. IGSN IDs can be used in the sample archiving process to share knowledge, providing information on what available resources a facility has, and thus what can be made discoverable to support internal and external research.

Linking the digital representation of a sample back to the physical object may be achieved in a variety of ways. The most common method is to simply permanently affix a label or to write/engrave the IGSN ID onto the sample or its container. It is convenient if creating labels to include QR codes or barcodes that encode IGSN IDs as actionable URIs. This then enables machine-readable identification of samples and links them to their metadata records/landing pages.

One must also remember that owing to their physical nature, material samples are often handled by humans, and therefore labels should also include human-readable information such as local accession or inventory numbers. We have created simple [display guidance](https://support.datacite.org/docs/displaying-igsn-ids) for IGSN IDs, including for labelling. However, best practices are still developing, and we will continue to update the guidance as we talk with more disciplinary communities. 

### Tracking – Sample Process Management

Since material samples are physical objects, they may be moved from one physical location to another as part of the sample lifecycle. Local systems for unique identification of samples have limited scope. Samples names can often change at each stage of the sample management process, making it difficult to track samples across institutional and system boundaries. Outside of institutional boundaries, it is often more likely that an identifier is ambiguous for an external organization.

IGSN IDs are unambiguous, globally unique identifiers. Whilst IGSN IDs may be assigned to a material sample at any stage of its lifecycle, the most effective way to avoid ambiguity is to apply IGSN IDs as early as possible. It is highly recommended to assign an IGSN ID to a material sample at its ‘birth’; namely, as soon as it is collected in the field or synthesized in a laboratory. Tools such as electronic field notebooks can assist in document processes during field sampling activities, and DataCite features such as pre-assignment and batch issuing of IGSN IDs in the [Draft state](https://support.datacite.org/docs/doi-states) can support workflows. In particular, in the earliest stages of the sample lifecycle, metadata might be limited or Internet connection may be unstable or unavailable.

Encoding IGSN IDs in QR codes or barcodes can be helpful in tracking progress, which might be read by field-based tools, or by readers installed at various stations within a facility. Such methods also enable integration of IGSN IDs into analytical systems, which can then access any sample metadata required for an analysis, and also update sample descriptions in DataCite metadata from information established as a result of the analysis.

A caveat of the above is that without a centralized barcode system, sample tracking still relies on people, and thus human errors can occur. To reduce errors, it may be valuable to encode IGSN ID suffixes to match local naming conventions used (for example) for a specific sampling campaign. Local identifiers in use are then simply transformed into globally unique ones through the appending of the IGSN ID prefix (10.xxxxx). 

IGSN IDs thus enable material samples to be tracked throughout different stages of the sample lifecycle and across laboratories and repositories. They furthermore can be generated without changes to established working procedures, naming conventions, or data systems.

### Cross-linking & Citation – Discovery and Credit

If a material sample is not assigned with a PID, then it is difficult to unambiguously describe the relation between a material sample, and datasets about the sample or scholarly literature in which the sample is cited.

In the [DataCite Metadata Schema](https://support.datacite.org/docs/datacite-metadata-schema-44), IGSN IDs enable a material sample to be [cross-linked with other entities](https://support.datacite.org/docs/enriching-igsn-id-metadata-in-the-datacite-metadata-schema#building-relationships-between-igsn-ids-and-other-resources-that-use-pids) by referencing the PIDs of the entities in `relatedIdentifier` metadata and describing the nature of the relationship with the sample via [`relationType`](https://support.datacite.org/docs/connecting-to-works). IGSN IDs are also actionable PID links that can be integrated into publications and datasets to connect them to contextual information in the online sample descriptions held in metadata records or landing pages. They can also be included in dataset metadata, and thus enable discovery in research data repositories and portals harvesting metadata.

An associated consideration is that current citation of samples is highly inconsistent among authors, articles, and journals. The [display guidance](https://support.datacite.org/docs/displaying-igsn-ids) for IGSN IDs generated by DataCite and the IGSN e.V. contains what is currently considered best practice for incorporation of IGSN IDs into citations and data tables. These best practices may evolve as we talk with stakeholders and reach consensus. In particular, we hope to reach a high level of standardization among major publishers.

### Sample Relationships – Linking Collection Sites and (Sub)Samples

Similar to the previous use case, it is difficult to unambiguously link parent samples and derived (subsample) children, if material samples are not assigned PIDs. By using the [`relationType`](https://support.datacite.org/docs/connecting-to-works) attribute in the [DataCite Metadata Schema](https://support.datacite.org/docs/datacite-metadata-schema-44), IGSN IDs that identify subsamples of sample can be related to each other, and thus mirror the hierarchical relationships among samples. 

An additional consideration for material samples collected in the field, is that the site at which the sampling activity took place is highly connected to the samples obtained. To represent this connection, collection sites also require PIDs to unambiguously link them to samples. As mentioned in the previous section, IGSN IDs may be registered for physical objects that are not ‘samples’ themselves, but rather features-of-interest from which a number of samples have been taken. Collection sites can therefore be individually identified using IGSN IDs. Each sample is then representative of its feature-of-interest, and can effectively be considered a child ‘subsample’ of the parent collection site. These IGSN IDs can be related to one another using [`relatedIdentifier`](https://support.datacite.org/docs/connecting-to-works) to match the hierarchical relationship.