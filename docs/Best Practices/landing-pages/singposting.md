---
title: singposting
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
Landing pages support humans that interact with scholarly objects on the web, providing descriptive metadata and links to content. These pages are not optimized for use by machine agents that navigate the scholarly web. For example, how can a robot determine which links on the myriad of landing pages lead to content and which to metadata? Signposting caters to machine agents by providing this information, and more, in a standards-based way. It contributes to FAIR's Findable, Accessible, and Reusable by uniformly conveying to machines what the persistent identifier of a scholarly object is, where its landing page is, where and what its content is, where metadata that describes it is, and what the persistent identifier of its author is. It conveys this by means of meaningful links that have web locations (HTTP URIs) as their target. As such it does significantly more than merely providing the information. It invites machine agents to follow the links to their target location on the web, and hopefully find further information and links there. It essentially provides them with a map to guide their travels across the scholarly web. Signposting contributes to FAIR's Interoperable through its uniform approach and because it is entirely based on widely implemented web protocols specified in IETF RFCs. As such, the interoperability that results from adopting it is not restricted to the scholarly landscape but encompasses the web at large.

[block:code]
{
  "codes": [
    {
      "code": "<link href=\"https://doi.org/10.1594/PANGAEA.932235\" rel=\"identifier\">\n<link href=\"https://doi.org/10.1594/PANGAEA.932235\" rel=\"describedby\" type=\"application/vnd.datacite.datacite+xml\">\n<link href=\"https://doi.org/10.1594/PANGAEA.932235\" rel=\"describedby\" type=\"application/vnd.citationstyles.csl+json\">\n<link href=\"https://doi.org/10.1594/PANGAEA.932235\" rel=\"describedby\" type=\"application/x-bibtex\">\n",
      "language": "html"
    }
  ]
}
[/block]
An example of a repository page using a wider range of metadata can be found here: [https://doi.org/10.1594/PANGAEA.932235](https://doi.org/10.1594/PANGAEA.932235)

If you’re not sure whether your repository landing pages contain the appropriate structured data, you can test them using Google’s [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool).

More information about [mapping different metadata formats](doc:how-can-i-map-different-metadata-formats-to-the-datacite-xml).