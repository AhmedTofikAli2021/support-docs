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
The DataCite Stats portal is open and freely accessible. Members, Users, and the whole community can check the information provided, compare it and reuse it to extract conclusions.
[block:api-header]
{
  "type": "basic",
  "title": "Registrations by Members"
}
[/block]
The top left tab of the interface provides access to the registration stats by Member (allocator). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e9c8d6-Screen_Shot_2017-02-27_at_12.41.11.png",
        "Screen Shot 2017-02-27 at 12.41.11.png",
        2422,
        934,
        "#ebeeee"
      ]
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
        "https://files.readme.io/eec75b7-Screen_Shot_2017-02-27_at_12.44.23.png",
        "Screen Shot 2017-02-27 at 12.44.23.png",
        2422,
        886,
        "#e8ecec"
      ]
    }
  ]
}
[/block]
By clicking the name of an Allocator (Member), you can display all the Data Centers (Users) working with the selected Member. Every filter used will appear on the top left of the page. They can be removed by clicking the red cross button on their left side.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b79cc8-Screen_Shot_2017-02-27_at_12.46.11.png",
        "Screen Shot 2017-02-27 at 12.46.11.png",
        2400,
        834,
        "#e8ecec"
      ]
    }
  ]
}
[/block]
The 'Searchable' results are also clickable. They will redirect to the (old) DataCite search interface, where you will see a complete list of all the DOIs minted by the selected organisation.
[block:api-header]
{
  "type": "basic",
  "title": "Registrations by Data Centers"
}
[/block]
The second tab from the left provides access to the registration stats by Data Center (User).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/471f4a5-Screen_Shot_2017-02-27_at_12.47.06.png",
        "Screen Shot 2017-02-27 at 12.47.06.png",
        2404,
        816,
        "#e7ecec"
      ]
    }
  ]
}
[/block]
This is a long list of more than 800 Data Centers. Using the arrows on each column, it is possible to sort the results, one characteristic at a time, for example by number of DOIs registered last week:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/faaa985-Screen_Shot_2017-02-27_at_12.44.47.png",
        "Screen Shot 2017-02-27 at 12.44.47.png",
        564,
        524,
        "#e8efef"
      ]
    }
  ]
}
[/block]
By clicking the name of a Data Center (User), you can display all the prefixes used by the selected User. Every filter used will appear on the top left of the page. They can be removed by clicking the red cross button on their left side.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c6870a-Screen_Shot_2017-02-27_at_12.45.32.png",
        "Screen Shot 2017-02-27 at 12.45.32.png",
        2420,
        586,
        "#e7e9e9"
      ]
    }
  ]
}
[/block]
The 'Searchable' results are also clickable. They will redirect to the (old) DataCite search interface, where you will see a complete list of all the DOIs minted by the selected organisation.
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
        "https://files.readme.io/e38357d-Screen_Shot_2017-02-27_at_12.47.38.png",
        "Screen Shot 2017-02-27 at 12.47.38.png",
        2394,
        738,
        "#e7ecec"
      ]
    }
  ]
}
[/block]
This is a long list of hundreds of prefixes. To find a particular prefix, you can sort them by number or use your browser's search. 

Using the arrows on each column, it is possible to sort the results, one characteristic at a time, for example by number of DOIs registered this year:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4fc8056-Screen_Shot_2017-02-27_at_12.48.08.png",
        "Screen Shot 2017-02-27 at 12.48.08.png",
        1090,
        554,
        "#eaf2f2"
      ]
    }
  ]
}
[/block]
By clicking a prefix, you can display the resolution stats by month, for that particular prefix. Every filter used will appear on the top left of the page. They can be removed by clicking the red cross button on their left side.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f4b8b1-Screen_Shot_2017-02-27_at_12.49.09.png",
        "Screen Shot 2017-02-27 at 12.49.09.png",
        2402,
        974,
        "#e6e9e9"
      ]
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
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]