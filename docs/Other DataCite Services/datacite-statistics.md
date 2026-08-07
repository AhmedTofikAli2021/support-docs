---
title: DataCite Statistics
excerpt: User Documentation
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Access the DataCite Statistics web interface here: [http://stats.datacite.org](http://stats.datacite.org) 
[block:api-header]
{
  "type": "basic",
  "title": "What is DataCite Stats?"
}
[/block]
DataCite provides statistics for both DOI registrations and DOI resolutions, filtered by Member, Data Center or Prefix via our DataCite Metadata Stats service.

Registration statistics relate to datasets that have been uploaded and received a DataCite DOI, while resolution statistics provide information on how often a DOI has been accessed.
[block:api-header]
{
  "type": "basic",
  "title": "Who can use DataCite Stats?"
}
[/block]
The DataCite Stats portal is open and freely accessible. Members, Clients, and the whole community can check the information provided, compare it and reuse it to extract conclusions.
[block:api-header]
{
  "type": "basic",
  "title": "Registrations by Members"
}
[/block]
The top left tab of the interface provides access to the registration stats by Member. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2131e15-Screenshot_2019-04-23_at_10.22.30.png",
        "Screenshot 2019-04-23 at 10.22.30.png",
        1297,
        620,
        "#ededed"
      ],
      "border": true
    }
  ]
}
[/block]
Using the arrows on each column, it is possible to sort the results, one characteristic at a time, for example by number of total DOI registrations:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce66bf0-Screenshot_2019-04-23_at_10.24.32.png",
        "Screenshot 2019-04-23 at 10.24.32.png",
        1278,
        622,
        "#ececec"
      ],
      "border": true
    }
  ]
}
[/block]
By clicking the name of a Member, you can display all the Clients working with the selected Member. The breadcrumbs above the table (pictured below as "Statistics / ANDS") will allow you to backtrack to a less filtered state. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e94ff78-Screenshot_2019-04-23_at_10.26.38.png",
        "Screenshot 2019-04-23 at 10.26.38.png",
        1414,
        691,
        "#ededed"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Registrations by Data Centers"
}
[/block]
The second tab from the left provides access to the registration stats by Client.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2654cd-Screenshot_2019-04-23_at_10.31.59.png",
        "Screenshot 2019-04-23 at 10.31.59.png",
        1349,
        682,
        "#edeeee"
      ],
      "border": true
    }
  ]
}
[/block]
This is a long list of more than 1000 Data Centers. Using the arrows on each column, it is possible to sort the results one characteristic at a time, for example by number of DOIs registered this month. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5a5522-Screenshot_2019-04-23_at_10.33.30.png",
        "Screenshot 2019-04-23 at 10.33.30.png",
        403,
        261,
        "#e7e7e7"
      ],
      "border": true
    }
  ]
}
[/block]
By clicking the name of a Client, you can display all the prefixes used by the selected Client. The breadcrumbs above the table (pictured below as "Statistics / DATACITE.BLOG") will allow you to backtrack to a less filtered state. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05d61ba-Screenshot_2019-04-23_at_10.36.12.png",
        "Screenshot 2019-04-23 at 10.36.12.png",
        1346,
        309,
        "#eaeaea"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Registration by Prefixes"
}
[/block]
The third tab from the left provides access to the registration stats by prefix.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f300af0-Screenshot_2019-04-23_at_10.37.32.png",
        "Screenshot 2019-04-23 at 10.37.32.png",
        1340,
        512,
        "#edeeee"
      ],
      "border": true
    }
  ]
}
[/block]
This is a long list of hundreds of prefixes. To find a particular prefix, you can sort them by number or use your browser's search. 

Using the arrows on each column, it is possible to sort the results, one characteristic at a time, for example by number of DOIs registered this month:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b21d67f-Screenshot_2019-04-23_at_10.39.05.png",
        "Screenshot 2019-04-23 at 10.39.05.png",
        403,
        247,
        "#e7e7e7"
      ],
      "border": true
    }
  ]
}
[/block]
By clicking a prefix, you can display the resolution stats by month, for that particular prefix. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/004f878-Screenshot_2019-04-23_at_10.42.20.png",
        "Screenshot 2019-04-23 at 10.42.20.png",
        1353,
        462,
        "#eceeee"
      ],
      "border": true
    }
  ]
}
[/block]
You can choose the month you want to explore using the drop down menu on the top left of the list, under the main tabs.

Regarding the information displayed, each column contains:

* Total attempted: Number of DOI resolutions requested during the selected month under the selected prefix, the number of times someone used the DOI to access the resource.
* Successful: Out of the total attempted, how many times it was possible to resolve the DOI name correctly.
* Failed: Out of the total attempted, how many times it was not possible to resolve the DOI name correctly. Note that this may be because the attempted DOI does not exist.

(Successful + Failed = Total attempted)

* Total unique DOIs: Number of different DOIs attempted during the selected month under the selected prefix. 
* Unique DOI successes: Out of the total unique DOIs requested, how many were successfully resolved every time they were requested.
* Unique DOI failures: Out of the total unique DOIs requested, how many were not successfully resolved.

(Unique DOI successes + Unique DOI failures = Total unique DOIs)

* Top 10 DOIs, successes: The 10 DOI names that were successfully resolved the most times during the selected period. These results are linked, so it is easy to resolve the DOI or check its metadata form the interface.

* Top 10 DOIs, failures: The 10 DOI names under the current prefix that couldn't be resolved. This list useful to find wrong links (codification problems, transcription mistakes, etc.) and fix them. The results are also linked, so it is easy to test and report the problem.
[block:api-header]
{
  "title": "CSV Download"
}
[/block]
You can download a CSV of the information you're looking at by clicking on the Download CSV button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/01ff48c-Screenshot_2019-04-29_at_08.26.14.png",
        "Screenshot 2019-04-29 at 08.26.14.png",
        1383,
        537,
        "#ededed"
      ],
      "border": true
    }
  ]
}
[/block]
The CSV will contain all the information that is currently on the screen. For example, in the screenshot above the user is looking at the main Statistics page showing DOI registrations for all Providers. Clicking the Download CSV button will download a CSV file that contains all of this information. If you would like a CSV that contains only your DOI registrations, first filter the view to show only your Client, and then click Download CSV. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4bac306-Screenshot_2019-04-29_at_08.35.32.png",
        "Screenshot 2019-04-29 at 08.35.32.png",
        1384,
        328,
        "#e7e6e6"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Retrieving statistics via API"
}
[/block]
You can retrieve any of the information in the DataCite Statistics portal via our REST API. See the [REST API reference for more information](ref:introduction).
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]