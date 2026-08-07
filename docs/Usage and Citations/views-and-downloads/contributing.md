---
title: Contributing views and downloads
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
Once you have your logs processed you will need to format them into reports and send them to DataCite.


## Formatting processed logs into reports

The First step in formatting your processed logs into reports is to read the CoP. You can review the [CoP section 4](https://www.projectcounter.org/code-of-practice-rd-sections/4-reports/) for more details about the fields. The reports format serialization is JSON. The format closely follows the [RESEARCH_DATA_SUSHI specification](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/). Below you can see an example:


```json
{
  "report-header": {
    "report-name": "dataset report",
    "report-id": "dsr",
    "release": "rd1",
    "created": "2016-09-08t22:47:31z",
    "created-by": "dataone",
		"reporting-period": 
    {
        "begin-date": "2018-05-01",
        "end-date": "2018-05-30"
    },
    "report-filters": [
      {
        "name": "begin-date",
        "value": "2015-01"
      }
    ],
    "report-attributes": [
      {
        "name": "exclude-monthly-details",
        "value": "true"
      }
    ],
    "exceptions": [
      {
        "code": 3040,
        "severity": "warning",
        "message": "partial data returned.",
        "help-url": "string",
        "data": "usage data has not been processed for all requested months."
      }
    ]
  },
  "report-datasets": [
    {
      "dataset-title": "lake erie fish community data",
      "dataset-id": [
        {
          "type": "doi",
          "value": "0931-865"
        }
      ],
      "dataset-contributors": [
        {
          "type": "name",
          "value": "john smith"
        }
      ],
      "dataset-dates": [
        {
          "type": "pub-date",
          "value": "2002-01-15"
        }
      ],
      "dataset-attributes": [
        {
          "type": "dataset-version",
          "value": "vor"
        }
      ],
      "platform": "dataone",
      "publisher": "dataone",
      "publisher-id": [
        {
          "type": "orcid",
          "value": "1234-1234-1234-1234"
        }
      ],
      "data-type": "dataset",
      "yop": "2010",
      "performance": [
        {
          "period": {
            "begin-date": "2015-01-01",
            "end-date": "2015-01-31"
          },
          "instance": [
            {
              "metric-type": "total-dataset-requests",
              "access-method": "regular",
              "count": 21
            }
          ]
        }
      ]
    }
  ]
}

```

### Key and Values

The allowed and recommended characters for an URL safe naming of parameters are defined in the format spec. To also standardize parameters names, the following (more restrictive) rules are recommended:

- Parameters names SHOULD start and end with the characters “a-z” (U+0061 to U+007A)
- Parameters names SHOULD contain only the characters “a-z” (U+0061 to U+007A), “0-9” (U+0030 to U+0039), and the hyphen minus (U+002D HYPHEN-MINUS, “-“) as separator between multiple words.



## Contributing to DataCite

The Usage Report API is the main point of contribution to usage reports. Please go ahead to the API Guide for all the details.
[block:html]
{
  "html": "<div>\n\n<a style=\"width:100%\"  href=\"https://support.datacite.org/docs/usage-reports-api-guide\" class=\"btn btn-primary btn-lg btn-block\" role=\"button\" aria-pressed=\"true\">Usage Reports API</a>\n\n \n</div>\n"
}
[/block]