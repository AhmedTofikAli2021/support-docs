---
title: What does the DOI, registered, created and last updated mean?
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
The timestamp “DOI last updated” that you see on the left of the DOI record in Fabrica indicates the last time the DOI was touched by something. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04ea736-lastupdated.png",
        "lastupdated.png",
        340,
        209,
        "#f6f4f4"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
As well as updates to the DOI record by a user, the timestamp also changes following internal updates from DataCite. Re-indexing is the most typical reason. However, there are many reasons for this timestamp to change and does not indicate that the metadata was updated. This feature is useful for things like caching.

The created date is the date the DOI is registered in the DataCite system. The registered date refers to when it was "registered" in the global handle server. If using a "draft" state workflow, these created and register date and time could be different.