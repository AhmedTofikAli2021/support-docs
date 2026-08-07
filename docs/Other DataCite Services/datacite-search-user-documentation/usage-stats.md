---
title: Usage Stats in DataCite Search
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
DataCite Clients can submit usage reports for the datasets in their repositories via our usage reports API. These usage reports should follow the [COUNTER Codes of Practice](https://www.projectcounter.org) relevant for the type of materials in the repository. The [DataCite Usage Reports API Guide](doc:usage-reports-api-guide) has more information on how to send usage reports for research data. If you are interested in sending usage reports for other types of materials, please contact us first at [support@datacite.org](mailto:support@datacite.org).  

Information from these usage reports appears as counts of "Views" and "Downloads" on individual DOI records within DataCite Search. 

##Where do these numbers come from? 
The counts that are shown correspond to the usage for an item recorded by the participating repository according to COUNTER processing rules. These processing rules attempt to exclude all usage that isn't intended by a user. This means filtering out double clicks and filtering out Internet robots and crawlers. Additionally, the information DataCite shows for each category is the "unique" count, meaning that events occurring within the same unique user session are counted as a single view or download. For full details on what is excluded, see the [COUNTER website](https://projectcounter.org) for the relevant Code of Practice.

##What are "views"? 
Views represent a retrieval of the item in any way, whether the content was accessed or downloaded in full or in part. The information DataCite displays as "view" is equivalent to "unique investigations" in COUNTER terminology. Downloads are a subset of views. 

##What are "downloads"?
Downloads represent the retrieval of all or part of the files within the item. The information DataCite displays as "downloads" is equivalent to "unique requests" in COUNTER terminology. Downloads are a subset of views. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/befed89-usagediagram.png",
        "usagediagram.png",
        477,
        516,
        "#73a4d2"
      ],
      "border": false,
      "caption": "DataCite usage terminology explained"
    }
  ]
}
[/block]
##The DOI I'm interested in has a note saying the data center is not submitting usage information. What do I do? 
If you are the manager of the data center, please see the [DataCite Usage Reports API Guide](doc:usage-reports-api-guide) for information on how to begin sending usage reports to DataCite. Participation is completely voluntary and there are no additional costs for participating. 

If you are not the manager of the data center, you may reach out to the data center in question to ask about usage stats. Please keep in mind that usage stats for research data is a relatively new initiative, so the data center may not yet have the capacity to participate.