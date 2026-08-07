---
title: Contributing Citations and References
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
Citations and references can be created by adding **relatedIdentifiers** to DataCite DOI metadata. Each relatedIdentifier has a required relationType attribute which is used to denote the type of relationship.

You can add citations and references to DOI metadata when you create the DOI initially and with subsequent updates to the metadata.

> 📘 What is the difference between a citation and a reference?
> 
> Citations are incoming pointers to a given research output.
> 
> - As in: “This dataset has 2 citations; it has been cited 2 times.”
> 
> References are outgoing pointers to other research outputs.
> 
> - As in: “This paper has 40 references in the references section.”

**Citations** for a DOI (“A”) from another DOI (“B”) can be generated using these relationTypes:

- IsCitedBy
  - A is cited by B
- IsReferencedBy
  - A is referenced by B
- IsSupplementTo
  - A is supplement to B

The inverse of a citation is a reference. Each of the three relationTypes for citations has an inverse relationType that can be used for a reference

**References** from a DOI (“A”) to another DOI (“B”) can be generated using these relationTypes:

- Cites
  - A cites B
- References
  - A references B
- IsSupplementedBy
  - A is supplemented By B

This table summarize the six relationTypes used for citations and references:

| relationType in metadata for DOI "A" | Relationship between A and B | Equivalent to          | Counts as citation for | Counts as reference for |
| :----------------------------------- | :--------------------------- | :--------------------- | :--------------------- | :---------------------- |
| IsCitedBy                            | A is cited by B              | B cites A              | A                      | B                       |
| IsReferencedBy                       | A is referenced by B         | B references A         | A                      | B                       |
| IsSupplementTo                       | A is supplement to B         | B is supplemented by A | A                      | B                       |
| Cites                                | A cites B                    | B is cited by A        | B                      | A                       |
| References                           | A references B               | B is referenced by A   | B                      | A                       |
| IsSupplementedBy                     | A is supplemented by B       | B is supplement to A   | B                      | A                       |

## Examples

### Dataset is cited by journal article

A dataset has a DataCite DOI. After a journal article has cited this dataset, the repository hosting the data wants to update the DOI metadata to reflect this. 

In this scenario, the dataset is cited by (IsCitedBy) the article (10.5438/ExampleArticle). The data repository adds the following relatedIdentifier:

```xml
<relatedIdentifier relatedIdentifierType="DOI" relationType="IsCitedBy">10.5438/ExampleArticle</relatedIdentifier>
```

Alternatively, the repository could use the relationType IsReferencedBy or IsSupplementTo. Any of these relationTypes will count as one citation for the dataset.

### Dataset references a paper

A dataset has a DataCite DOI. The researcher has provided a README file to the data repository. This README file has a list of references for the dataset, including a paper published several years prior describing the data collection protocol that was applied.

In this scenario, the dataset references the earlier data collection protocol paper. The data repository includes the following relatedIdentifier:

```xml
<relatedIdentifier relatedIdentifierType="DOI" relationType="References">10.5438/ExamplePaper</relatedIdentifier>
```

Alternatively, the repository could use the relationType Cites or IsSupplementedBy.

### Preprint cites a dataset

A preprint has a DataCite DOI. The author has provided a list of references for the preprint, including a link to their dataset in a different repository.

In this scenario, the preprint cites the data. The preprint repository includes the following relatedIdentifier:

```xml
<relatedIdentifier relatedIdentifierType="DOI" relationType="Cites">10.5438/ExampleDataset</relatedIdentifier>
```

Alternatively, the repository could use the relationType References or IsSupplementedBy.

> 📘 How do I choose between the different relationTypes for citations and references?
> 
> The three relationTypes used for citations—IsCitedBy, IsReferencedBy, and IsSupplementTo—are all processed the same way by DataCite Event Data. Repositories can choose any of the three types that best suits their use case.
> 
> Similarly, the three relationTypes used for references—Cites, References, and IsSupplementTo—receive the same processing.

\*_DataCite citation workflow infographic _  
download: [png](https://datacite.org/wp-content/uploads/2023/08/DataCite-Citation-Workflow-2022.png) [pdf](https://datacite.org/wp-content/uploads/2023/08/DataCite-Citation-Workflow-2022.pdf) 

![](https://files.readme.io/a290a84-DataCite_Citation_Workflow_2022.png "DataCite Citation Workflow 2022.png")