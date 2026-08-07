---
title: Displaying Usage and Citations in your Repository
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
The Data Metrics Badge allows you to display usage and citations information in your repository. The _Data Metrics Badge_ provides an open and easy way to display the numbers of citations and usage statistics that your research datasets and resources have received. 

The Data Metrics Badge was created as part of the [PARSEC](http://www.belmontforum.org/projects/4057/) project, Building New Tools for Data Sharing and Reuse through a Transnational Investigation of the Socioeconomic Impacts of Protected Areas. 

The _Data Metrics Badge_ can be easily embedded on your repository landing page and will display usage and citations metrics retrieved from DataCite Services. Usage statistics are processed according to the [Code of Practice for Research Data](https://www.projectcounter.org/code-practice-research-data/). Citations stats are collected via the [Event Data](doc:eventdata-guide).

> 👍 
> 
> This work is supported by the Belmont Forum as an output of the PARSEC project, with funds specifically provided by the National Science Foundation under Grant Number 1929464

## How-To

To embed the badge in your repository just add the following code within the `<body>` of your landing pages and modify the DOI property in the  `<data-metrics-badge>` according to your landing page's DOI.

```html
<body>
  <script src="https://unpkg.com/vue@^2/dist/vue.min.js"></script>
    <script src="https://unpkg.com/@webcomponents/webcomponentsjs@2.0.0/webcomponents-loader.js"></script>
  <script src="https://unpkg.com/data-metrics-badge/dist/data-metrics-badge.min.js"></script>
  <data-metrics-badge doi="10.7272/q6g15xs4" display="regular"></data-metrics-badge>
</body>
```



That will display the Data Metrics Badge as is shown below and you could choose between different types of badge. One can change the type of badge by changing the `display` property to either: `small` or `regular`.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a95c277-small.png",
        "small.png",
        836
      ],
      "align": "center",
      "caption": "Small"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d80a08c-regular.png",
        "regular.png",
        702
      ],
      "align": "center",
      "caption": "Regular size"
    }
  ]
}
[/block]

[block:html]
{
  "html": "<script src=\"https://unpkg.com/vue@^2/dist/vue.min.js\"></script>\n    <script src=\"https://unpkg.com/@webcomponents/webcomponentsjs@2.0.0/webcomponents-loader.js\"></script>\n<script src=\"https://unpkg.com/data-metrics-badge/dist/data-metrics-badge.min.js\"></script>\n\n \n\n\n\n\n    <div class=\"row\">\n        <div class=\"\">  \n</div>\n        <div> <data-metrics-badge doi=\"10.7272/q6g15xs4\" display=\"regular\"  ></data-metrics-badge>\n</div>\n\n\n        <div class=\"col-sm-1\"></div>\n    </div>\n    <div class=\"row\">\n        \n        <div class=\"col-sm-6\">\n          <data-metrics-badge doi=\"10.6073/pasta/5a17c5689767d95056ec63842b981998\"></data-metrics-badge></div>\n        <div class=\"col-sm-1\"></div>\n    </div>\n   \n\n\n</div>\n\n<style>\n\n</style>"
}
[/block]



For more details visit:

<https://www.npmjs.com/package/data-metrics-badge>