---
title: Contributing Views and Downloads
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

## Format processed logs into reports

The reports format serialization is JSON. The format closely follows the [RESEARCH_DATA_SUSHI specification](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/). 

Example report:

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



## Contribute usage reports to DataCite

Contribute usage reports by using the [DataCite Usage Reports API](https://support.datacite.org/docs/usage-reports-api-guide).