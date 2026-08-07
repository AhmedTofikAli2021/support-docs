---
title: Considerations When Setting Up an IGSN Repository and Registration Workflow
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
When implementing IGSN IDs, it is important to explore what changes may be required within your institution’s organizational and technical infrastructure to support the registration of PIDs for material samples. The following is a set of questions that may need to be thought through internally by a DataCite Member or Consortium Organization when it is developing an IGSN ID workflow. The questions are non-exhaustive, and because they are organization-specific, we are unable to provide definitive answers. Instead, elaboration of each question is given, as well as some guidance.

## IGSN ID Repositories

### Can the Current System Handle Multiple Repositories/Prefixes?

Because IGSN IDs are functionally DOIs, [Fabrica](doc:doi-fabrica) and [DataCite APIs](doc:api) can be used to create and modify IGSN IDs. However, it is not currently possible to recognize the difference between an IGSN ID for a material sample and a DOI for another type of research output at the metadata record level. To enable distinction of IGSN IDs, DataCite Members and Consortium Organizations are required to create at least one new, separate [IGSN ID Catalog Repository](doc:registering-igsn-ids) exclusively for registering IGSN IDs. Multiple Repositories and prefixes could be created to separate out specific sample types or collections. 

If an organization has already developed a system that integrates with DataCite DOI services through our APIs, this system may be designed in a way that it cannot manage more than one set of Repository credentials. In such cases, the organization needs to decide if it wants to:

1. Redesign its current system, or create a new one, to handle additional Repository credentials and prefixes.
2. Make a copy of its system, or create a new one, that is then used for the IGSN ID repository(ies) and prefix(es).
3. Use [software provided by a DataCite Service Provider](doc:service-provider-software-integrations) to manage IGSN ID registrations.

### Who Manages/Controls IGSN ID Repositories/Prefixes?

Depending on its institutional structure and/or policies, the management of DOI registration, and therefore control of any [DataCite Repository accounts](doc:datacite-account-types#repository-account), may be the responsibility of a particular department/division/unit within a DataCite Member or Consortium Organization. This might typically be the library in the case of a University or Research Institute.

An associated concern in some organizations is that because a PID is a long-term source of truth, there is a level of culpability involved in their creation and maintenance. In such organizations, it can thus be considered highly important that Repositories and prefixes are administered by information specialists through an internal service (and for which there will be a continuity plan), rather than by a research/disciplinary department in which projects and staff are more transient. 

In the case of material samples, they will often be collected, managed, and archived solely by (Principal Investigators (PIs) in) disciplinary departments, which hold the knowledge base and expertise about the samples. It may therefore make sense for whomever in a DataCite Member or Consortium Organization that primarily manages the top-level Member account to pass control of IGSN ID Repository accounts (i.e., the credentials to those accounts) to the disciplinary departments that require and will use IGSN IDs for their samples. At a minimum, domain experts should ideally be included in the discussions and decisions for IGSN IDs. 

Factors that may feed into such decisions include:

- Costs: Whose budget? For what? How? The scale of usage of IGSN IDs for material samples may be high in comparison to other research outputs. Note that, as per [DataCite’s fee model](https://datacite.org/fee-model/#consortium), the number of DOIs (inc. IGSN IDs) that a Consortium Organization can register annually is limited. 
- Technical: Who sets up and manages registration workflows? What technical knowledge and resourcing will be needed to support a new IGSN ID Catalog Repository?

## Metadata

### What Metadata Sources are Available?

IGSN IDs are registered with metadata encoded in the [DataCite Metadata Schema](doc:/datacite-metadata-schema). To assist with entering material sample metadata into DataCite services, the IGSN e.V. and DataCite have developed a [recommendation](doc:igsn-id-metadata-recommendations) for the [Mandatory](https://datacite-metadata-schema.readthedocs.io/en/4/properties/overview/#mandatory-properties) and [Recommended](https://datacite-metadata-schema.readthedocs.io/en/4/properties/overview/#recommended-and-optional-properties) properties of the DataCite Metadata Schema. 

It is strongly recommended to populate as many properties as possible in the DataCite Metadata Schema. Providing rich metadata not only ensures that a material sample can be distinctly recognized, but also maximizes its discoverability by the disciplinary user community interested in accessing the sample information (and possibly the sample itself). An organization therefore needs to explore what local sample metadata has been collected for material samples that it wishes to assign IGSN IDs.

The types and depth of information available to DataCite Metadata Schema properties (and landing pages) may differ significantly among: material sample types, disciplines, departments, PIs/laboratories, or maybe even field campaigns. It is therefore valuable to get a comprehensive overview upfront of what sources of information can be used to enhance the discoverability of IGSN IDs. Discussions between information and domain experts may also be necessary to map local sample information to the DataCite Metadata Schema.

The partnership between the IGSN e.V. and DataCite is committed to ensuring that the DataCite Metadata Schema is enhanced to best support the needs of samples communities. To assist in this process, the partnership is setting up disciplinary Communities of Practice that will develop minimum and extended metadata profiles for their (sub-)domains. Mapping these profiles back to the DataCite Metadata Schema—in a similar way to the [IGSN–DataCite Crosswalk Recommendation](https://docs.google.com/document/u/0/d/16GTTvcnYvTDIYvypCq9dimNhDFK-fCipayO6YUngc90/edit)—enables any large gaps to be identified and to explore what changes might be needed to the DataCite Metadata Schema. 

### When Should a New Version of an IGSN ID be Registered?

Both features-of-interest (collection sites) and material samples may evolve over time. A simple example is in agriculture, where the same piece of land might be subjected to different controlled conditions depending on the year. Although the location did not change, the material samples taken each time will be inherently linked to the conditions the land was under.

The questions an organization may therefore need to ask itself are:

1. Should an IGSN ID ever be [versioned](doc:versioning)?
2. If so, at what point is the physical object/location it is linked to, no longer the same object/location? What are the prerequisites for triggering a new IGSN ID?

These types of questions are difficult to answer for any research output, and are especially complex for material samples. Corrections to errors or small updates to the metadata will unlikely warrant the creation of a new version. Moreover, the state of a material sample can be updated within a metadata record using the [`date`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/date/) property with the applicable `dateType`. The main consideration is whether it is important for (sub)samples/data/publications/… to reference a feature-of-interest or material sample as it was at a point in time. In this case, an organization may decide that a way is needed for users to access different versions of the feature-of-interest or sample with a clear indication of what is the most up-to-date version.

### How is Embargoed Information Dealt With?

It is fairly common for research organizations to have an embargo period during which only a limited set of people have access to the (meta)data. Such an embargo period may end either after a set amount of time or once the results of the research are published. Even if an organization does not have an embargo period, it may in some cases want the (meta)data to be kept private because of regulations or otherwise (e.g., to protect the collection site).

What sample information is listed in a metadata record and/or landing page of an IGSN ID is at the discretion of the organization registering the IGSN ID in DataCite services. For [DataCite Metadata Schema](doc:/datacite-metadata-schema) properties where a value is unknown or cannot be released, there is a set of [standard values](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-3/) that can be used. This is true even for many of the [Mandatory properties](https://datacite-metadata-schema.readthedocs.io/en/4/properties/overview/#mandatory-properties). These values are then stored in our systems until the organization wishes to update them because metadata is now available or can be made public. 

Unless outsourced to a [DataCite Service Provider](doc:datacite-service-providers), landing pages are created by a DataCite Member or Consortium Organization. Thus, the information contained in a landing page can be completely tailored to institutional/community needs. Sensitive information may be omitted or blurred (e.g., location information may be included at a coarser granularity). A note may also be added that some information is available upon request, what are the conditions for access, and who to contact. Ideally, it should be made known what information has been collected for the sample. That can be achieved by sharing the metadata schema used for the sample through the [`relationType`](https://datacite-metadata-schema.readthedocs.io/en/4/properties/relatedidentifier/#b-relationtype) 'HasMetadata' and/or in the landing page.

DataCite Members and Consortium Organizations may choose to maintain IGSN IDs in the Draft or Registered state during an embargo period, before changing them to Findable once they can be made publicly available. It should be noted that IGSN ID metadata in **any** state is visible to other authenticated DataCite account holders using our Member API. IGSN ID metadata therefore should not contain information that must expressly be kept private. See our support documentation on [DOI States](doc:doi-states) and recommendations for [placeholder and sensitive IGSN ID metadata](doc:enriching-igsn-id-metadata-in-the-datacite-metadata-schema#placeholder-and-sensitive-metadata).

## Landing Pages

### What Elements are Needed for Landing Pages?

The types of metadata that are captured for material samples will almost certainly be significantly different to that captured for many other research outputs, and especially that for datasets. In turn, there will be major differences in the types of metadata wanted by the disciplinary user community to discover a material sample, determine if it is exactly the one they want, and how it might be reused.

The above gives rise to two immediate consequences that must be considered by a DataCite Member of Consortium Organization when beginning to register IGSN IDs for material samples:

1. It is unlikely that any template an organization has been using thus far to generate landing pages for other research outputs will be applicable to material samples. It might even be that the tool an organization is using to create pages is insufficiently flexible to customize the layout to be appropriate for material samples.
2. Discussions are needed with the domain experts who are collecting and managing the material samples, to ascertain what local sample metadata—and other sources of information—are being collected and which of these are considered as being vital for optimal discoverability and knowledge sharing. Pages might additionally include related items such as images, maps, and a structured way of highlighting the hierarchical connectivity among samples. You may also wish to add [schema.org markup to landing pages](doc:schemaorg).

An associated question is whether landing pages are common across departments or disciplines within an organization. Because the types and depth of available sample information has the potential to be highly variable, it may be difficult for a DataCite Member or Consortium Organization to reach agreement on a set of common properties for landing pages. Especially, such a set may either be so small that it provides limited information, or so large to cover all cases that pages are sparse or confusing to the disciplinary user community. A decision will again require deliberation with those wishing to register IGSN IDs.

### Who Creates and Hosts Landing Pages?

For many DataCite Members or Consortium Organizations, it is likely that the DOI landing pages of research outputs are managed by the same organizational service that is registering the DOIs. This means that information specialists typically generate and store landing pages rather than research or disciplinary departments. Alternatively, landing pages may be created using the software of a [DataCite Service Provider](doc:datacite-service-providers), which may or may not be flexible in the types of information that can be displayed; especially, if it does not yet support IGSN IDs for material samples.

The previous subsection has already highlighted the need to consult with domain experts on decisions around what should/must be included in landing pages. Moreover, it may be that an organization decides for one or more disciplinary departments to take over the responsibility of creating and hosting IGSN ID landing pages according to the needs of their user communities. These landing pages may be implemented within an existing system or could involve new samples-specific software separate from existing infrastructures for DOIs.

There may of course be budgetary and technical factors within an organization that preclude changes to current landing page management practices; however, at a minimum, it is expected that domain experts are included in the decision-making process.