---
title: Displaying Usage and Citations in your Repository
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
The Data Metrics Badge allows you to display usage and citations information in your repository. The *Data Metrics Badge* provides an open and easy way to display the numbers of citations and usage statistics that your research datasets and resources have received. 

The Data Metrics Badge was created as part of the [PARSEC](http://www.belmontforum.org/projects/4057/) project, Building New Tools for Data Sharing and Reuse through a Transnational Investigation of the Socioeconomic Impacts of Protected Areas. 

The *Data Metrics Badge* can be easily embedded on your repository landing page and will display usage and citations metrics retrieved from DataCite Services. Usage statistics are processed according to the [Code of Practice for Research Data](https://www.projectcounter.org/code-practice-research-data/). Citations stats are collected via the [DataCite and Crossref EventData Service](https://blog.datacite.org/are-your-data-being-used-event-data-has-the-answer/). 


## How-To

To embed the badge in your repository just add the following code within the `<body>` of your landing pages and modify the DOI property in the  `<data-metrics-badge` according to your landing page's DOI.
[block:code]
{
  "codes": [
    {
      "code": "<body>\n  <script src=\"https://unpkg.com/vue/dist/vue.min.js\"></script>\n  <script src=\"https://unpkg.com/data-metrics-badge/dist/data-metrics-badge.min.js\"></script>\n  <data-metrics-badge doi=\"10.7272/q6g15xs4\" display=\"medium\"></data-metrics-badge>\n</body>\n",
      "language": "html"
    }
  ]
}
[/block]
That will display the Data Metrics Badge as is shown below and you could choose between different types of badge. One can change the type of badge by changing the `display` property to either: `small` or `medium`.
[block:html]
{
  "html": "<div class=\n\n<div>\n\n<script src=\"https://unpkg.com/vue/dist/vue.min.js\"></script>\n<script src=\"https://unpkg.com/data-metrics-badge/dist/data-metrics-badge.min.js\"></script>\n\n\n\n\n    <div class=\"row\">\n        <div class=\"col-sm-4\">  <p class=\"lead\">Medium Size widget</p>\n</div>\n        <div class=\"col-sm-6\"> <data-metrics-badge doi=\"10.7272/q6g15xs4\" display=\"medium\"></data-metrics-badge>\n</div>\n        <div class=\"col-sm-1\"></div>\n    </div>\n    <div class=\"row\">\n        <div class=\"col-sm-4\"><p class=\"lead\">Small size widget</p></div>\n        <div class=\"col-sm-6\"><data-metrics-badge doi=\"10.7272/q6g15xs4\" display=\"small\"></data-metrics-badge></div>\n        <div class=\"col-sm-1\"></div>\n    </div>\n   \n\n\n\n</div>\n\n<style></style>"
}
[/block]
For more details visit:

https://www.npmjs.com/package/data-metrics-badge