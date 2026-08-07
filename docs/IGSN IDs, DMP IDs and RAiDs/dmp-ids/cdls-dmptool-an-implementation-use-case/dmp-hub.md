---
title: The DMP Hub
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
The DMPHub is a repository for DMP metadata. It follows the new [RDA common standard metadata for DMPs](https://github.com/RDA-DMP-Common/RDA-DMP-Common-Standard) to be loaded via an API and acquires a DMP ID from Datacite. The two main functions of the system are to:

1. Assign DMP IDs 
 
2. Provide a landing page for the DMP ID with links back to the original document whether it be a PDF or a system like the DMPTool. See an example of a landing page here: [https://dmphub.cdlib.org/dmps/doi:10.48321/D17G67](https://dmphub.cdlib.org/dmps/doi:10.48321/D17G67)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/428643a-Screen_Shot_2021-03-31_at_11.54.25.png",
        "Screen Shot 2021-03-31 at 11.54.25.png",
        1260,
        850,
        "#edf2f1"
      ]
    }
  ]
}
[/block]
The BCO-DMO data contained metadata in line with the requirements of the RDA common standard and also contained related identifiers to the final research outputs. This information was loaded into the DMPHub via its API and DMP IDs were acquired.
 
The DMPHub’s data model follows the basic structure of the RDA metadata standard for DMPs and converts that information into the DataCite metadata schema when acquiring the DMP ID.
 
Once the DMP ID had been registered, it was possible to query the PID Graph and see the connections identified through the BCO-DMO data.