---
title: DataCite Search
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
Access the DataCite Search web interface here: [https://search.datacite.org](https://search.datacite.org) 
[block:api-header]
{
  "type": "basic",
  "title": "What is DataCite Search?"
}
[/block]
DataCite search is a web interface where you can explore the complete collection of DataCite DOIs. You can search, filter, cite results, push them to your ORCID profile, and more!
[block:api-header]
{
  "type": "basic",
  "title": "Who can use DataCite Search?"
}
[/block]
DataCite Search is open to the whole community. It is particularly designed to showcase the possibilities of the DataCite API and its metadata, while serving the community as a central search platform.
[block:api-header]
{
  "type": "basic",
  "title": "How to search?"
}
[/block]
DataCite Search uses the extended DISMAX query parser: 

[https://cwiki.apache.org/confluence/display/solr/The+Extended+DisMax+Query+Parser](https://cwiki.apache.org/confluence/display/solr/The+Extended+DisMax+Query+Parser)

This means that multiple search terms separated by space perform an OR operation, e.g `maths physics` will search for entries where the word `maths` or the word `physics` exist.

AND operations can be performed too by including the `+` symbol, e.g. `physics +experimental` will search for entries where both words exist.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/24f5d21-a.jpg",
        "a.jpg",
        1626,
        703,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
If you want both words to appear together in the order you are looking for, you can put them between quotes:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed3731e-b.jpg",
        "b.jpg",
        1606,
        937,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Facets"
}
[/block]
You can filter your results using the column on the right. These boxes are called facets, and will help you find the results you are looking for in an easier way.

Imagine you want to know more about the Standard Model. If you search for `"standard model" physics` you will find almost two thousand results:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af27b9c-Screen_Shot_2017-05-09_at_15.25.16.png",
        "Screen Shot 2017-05-09 at 15.25.16.png",
        1926,
        1366,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
If you use the facets on the right and choose Audiovisual content (under the Resource Types category) you will only see videos related to your query:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c8db574-Screen_Shot_2017-05-09_at_15.29.28.png",
        "Screen Shot 2017-05-09 at 15.29.28.png",
        1910,
        1228,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Cite results"
}
[/block]
DataCite search can export the results of your queries to different formats. Just click on the "Cite" button on the bottom bar of each search result and a pop-up window will show you all the available citation formats.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4dc3682-Screen_Shot_2017-05-09_at_15.31.30.png",
        "Screen Shot 2017-05-09 at 15.31.30.png",
        1806,
        464,
        "#775454"
      ]
    }
  ]
}
[/block]
These are the most common ones but, of course, you can always our [DataCite Citation Formatter](doc:datacite-citation-formatter) to produce more!
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8961d54-Screen_Shot_2017-05-09_at_15.33.22.png",
        "Screen Shot 2017-05-09 at 15.33.22.png",
        1834,
        648,
        "#e7e7e6"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Add to ORCID record"
}
[/block]
You can also use DataCite Search you update your ORCID record. Login using [DataCite Profiles](doc:datacite-profiles-user-documentation) and each one of the boxes will show you an "Add to ORCID record" button. Hit "OK" if you are sure it is your work, and we will take care of the rest! Your ORCID record will soon include your new information.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eec3966-Screen_Shot_2017-05-09_at_15.36.28.png",
        "Screen Shot 2017-05-09 at 15.36.28.png",
        1802,
        968,
        "#ebeded"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Remove from ORCID Record"
}
[/block]
Works that have been added to your ORCID record show the label "In your ORCID record", and you can remove them from your ORCID record by clicking on that label, and then "OK".
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70b265f-Bildschirmfoto_2017-07-03_um_16.21.46.png",
        "Bildschirmfoto 2017-07-03 um 16.21.46.png",
        1816,
        992,
        "#606f75"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]