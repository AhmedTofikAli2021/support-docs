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
You can access the DataCite Statistics web interface here: <http://stats.datacite.org>. DataCite Statistics is open and freely accessible to Members, Repositories, and the whole community. DataCite Statistics displays DOI registrations and DOI resolutions. 

**Registration statistics** 

The registration statistics refer to the number of DOIs that have been registered by a DataCite Member or Repository. The registration statistics can be filtered by Member account or Repository account.

> 📘 
> 
> The total DOI Registrations includes DOIs in Findable and Registered state.

**Resolution statistics **

The resolution statistics provide information on how many times a DOI has been accessed via the DOI link. The data is sent to DataCite by [CNRI](https://www.cnri.reston.va.us/)

## How to use DataCite Statistics

The first page shows registration statistics by Member. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/847b1ad-Screen_Shot_2020-02-10_at_10.32.16.png",
        "Screen Shot 2020-02-10 at 10.32.16.png",
        2494
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Using the arrows on each column you can sort the results by total DOI registrations, total registrations by year and current month. You can also sort the results by total Findable state DOIs Vs total Registered state DOIs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8480486-Screen_Shot_2020-02-10_at_10.33.04.png",
        "Screen Shot 2020-02-10 at 10.33.04.png",
        2498
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Click on the name of a Member to see the associated Repositories and total registrations for each Repository. 

> 📘 Consortia
> 
> The DataCite Statistics does not currently allow filtering by Consortium. Each Consortium Organization is displayed separately.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/54f15fd-Screenshot_2023-09-21_at_12.08.06.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 👍 
> 
> Use the breadcrumbs above the table to go back to the first page.

By clicking the name of a Repository, you will see the prefix used by the selected Repository. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cda03ae-Screenshot_2023-09-21_at_12.19.23.png",
        "Screenshot 2019-04-23 at 10.36.12.png",
        1346
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## CSV Download

You can download a CSV file of the information you're looking at by clicking on the Download CSV button. 

The CSV will contain all the information that is currently on the screen. If you are looking at the main statistics page showing DOI registrations for all Members, clicking the Download CSV button will download a CSV file that contains all of this information. 

If you would like a CSV that contains only the DOI registrations of your Member account, first filter the view to show only your Repository, and then click Download CSV.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52800c3-Screenshot_2023-09-21_at_12.39.03.png",
        "Screenshot 2019-04-29 at 08.26.14.png",
        1383
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## Resolution Statistics

When you click on a prefix you will see the resolution statistics for that prefix displayed in a table.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b960d82-Screenshot_2023-09-21_at_12.20.19.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


The resolution statistics table includes:

- Total attempted: Number of DOI resolutions requested during the selected month under the selected prefix, the number of times someone used the DOI to access the resource.
- Successful: Out of the total attempted, how many times it was possible to resolve the DOI name correctly.
- Failed: Out of the total attempted, how many times it was not possible to resolve the DOI name correctly. Note that this may be because the attempted DOI does not exist.

(Successful + Failed = Total attempted)

- Total unique DOIs: Number of different DOIs attempted during the selected month under the selected prefix. 
- Unique DOI successes: Out of the total unique DOIs requested, how many were successfully resolved every time they were requested.
- Unique DOI failures: Out of the total unique DOIs requested, how many were not successfully resolved.

(Unique DOI successes + Unique DOI failures = Total unique DOIs)

- Top 10 DOIs, successes: The 10 DOI names that were successfully resolved the most times during the selected period. These results are linked, so it is easy to resolve the DOI or check its metadata form the interface.

- Top 10 DOIs, failures: The 10 DOI names under the current prefix that couldn't be resolved. This list useful to find wrong links (codification problems, transcription mistakes, etc.) and fix them. The results are also linked, so it is easy to test and report the problem.

## Retrieving statistics via the REST API

You can retrieve the statistics displayed on DataCite Statistics using the totals endpoint with DataCite's REST API. See the [REST API reference for more information](ref:introduction).

To see the DOI registration statistics for all Members and Consortium Organizations, you can run the following query:

```shell shell
$ curl https://api.datacite.org/providers/totals
```

To see the DOI registration statistics for each Repository under a Member or Consortium Organization, you can run the following query:

```Text shell
$ curl https://api.datacite.org/clients/totals?provider-id=cern
```

To see the DOI registration statistics for a prefix assigned to a Repository:

```Text shell
$ curl https://api.datacite.org/prefixes/totals?client-id=cern.zenodo
```

"Resolutions by Month" statistics are only available on the DataCite Statistics web interface.

For more API queries see the [REST API documentation](doc:api).

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)