---
title: Project Tracking and Identification
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
DOIs can be assigned to projects. In the DataCite Metadata Schema, the resourceTypeGeneral Project is described as:

_A planned endeavor or activity, frequently collaborative, intended to achieve a particular aim using allocated resources such as budget, time, and expertise._

Below is an example of XML metadata for a DOI with the resourceTypeGeneral: Project:

```xml Project
<resourceType resourceTypeGeneral="Project">Field season</resourceType>
```

This resource type represents the project and includes research projects and studies. For a project deliverable or description of a project, use the corresponding resource type for the output—e.g., for a project report, dissertation, or study registration, use the resourceTypeGeneral “Report”, “Dissertation”, or “StudyRegistration” instead.

[RAiD Project Use Case](doc:raids): ‘RAiD’ is an acronym for 'Research Activity Identifier'. It is a unique, persistent identifier (PID) for research projects and activities. RAiD is developed, maintained, and operated by the Australian Research Data Commons (ARDC) in its role as Registration Authority under ISO 23527:2022, in cooperation with RAiD Registration Agencies.

[PID4NFDI Project DOI Use Case](https://doi.org/10.5281/zenodo.17743198): To ensure consistent, interoperable, and FAIR identification across the NFDI landscape, PID4NFDI recommends the use of DataCite Digital Object Identifiers (DOIs) with the resource type “Project” as the authoritative identifiers for NFDI consortia.