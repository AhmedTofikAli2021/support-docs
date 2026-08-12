---
title: Usage Reports Quick Guide
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
[block:api-header]
{
  "title": "Overview:"
}
[/block]
This quick guide provides links to some of the main resources needed when developing usage reporting for a repository.  There are detailed guides available below and we recommend you review them:

[Counter Code of Practice](counter-code-of-practice) 
[Processing views and downloads](doc:processing)
[Contributing views and downloads](doc:contributing)\
[Consuming views and downloads](doc:consuming)

[block:api-header]
{
  "title": "Reporting Quick Guide:"
}
[/block]
Some of the key points for sending views and downloads for DOIs to DataCite are listed below.

You need a processor implemented before the usage metrics can be generated. 

## Generate Usage Logs

Usage logs are generated following the Counter Code of Practice Guidelines. It is only possible to send views and downloads reports 
  * the elements that should be included in each report
  * the options that must be provided to enable a consumer to access the reports 
  * how to log transactions
  * the rules of log processing and basics for harvesting reports

## Transform the logs 

There are two options for transforming the logs:

Option 1: Use the Counter Processor, an open source Python application developed by California Digital Library, both Dataverse and Dryad use this. There is more information in this [video](https://support.datacite.org/docs/implementing-the-counter-code-of-practice-for-research-data-in-repositories#other-repositories-experiences) with comments from Dryad, Zenodo and Dataverse with more detail about using the processor.

Option 2: Develop an in house application

## Frequency of the logs

The reporting period is monthly (this is specified in the COUNTER standard). Within the monthly reporting period, one or multiple reports can be sent. For instance, a daily, weekly or (single) monthly report can be sent. Each report contains the total counts for each DOI as they stand at that point. 

## Usage events 

Usage events are included in the report for each DOI. Every DOI is listed with the total current counts for each metric provided. 

Examples are available by following the links below:
[Implementing the Counter Code of Practice for Research Data in Repositories](doc:implementing-the-counter-code-of-practice-for-research-data-in-repositories)
[Contributing views and downloads](doc:contributing)

Excerpt of a report: 
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"report-header\": {\n    \"report-name\": \"dataset report\",\n    \"report-id\": \"dsr\",\n    \"release\": \"rd1\",\n    \"created\": \"2016-09-08t22:47:31z\",\n    \"created-by\": \"dataone\",\n\t\t\"reporting-period\": \n    {\n        \"begin-date\": \"2018-05-01\",\n        \"end-date\": \"2018-05-30\"\n    },\n    \"report-filters\": [\n      {\n        \"name\": \"begin-date\",\n        \"value\": \"2015-01\"\n      }\n    ],\n    \"report-attributes\": [\n      {\n        \"name\": \"exclude-monthly-details\",\n        \"value\": \"true\"\n      }\n    ],\n    \"exceptions\": [\n      {\n        \"code\": 3040,\n        \"severity\": \"warning\",\n        \"message\": \"partial data returned.\",\n        \"help-url\": \"string\",\n        \"data\": \"usage data has not been processed for all requested months.\"\n      }\n    ]\n  },\n  \"report-datasets\": [\n    {\n      \"dataset-title\": \"lake erie fish community data\",\n      \"dataset-id\": [\n        {\n          \"type\": \"doi\",\n          \"value\": \"0931-865\"\n        }\n      ],\n      \"dataset-contributors\": [\n        {\n          \"type\": \"name\",\n          \"value\": \"john smith\"\n        }\n      ],\n      \"dataset-dates\": [\n        {\n          \"type\": \"pub-date\",\n          \"value\": \"2002-01-15\"\n        }\n      ],\n      \"dataset-attributes\": [\n        {\n          \"type\": \"dataset-version\",\n          \"value\": \"vor\"\n        }\n      ],\n      \"platform\": \"dataone\",\n      \"publisher\": \"dataone\",\n      \"publisher-id\": [\n        {\n          \"type\": \"orcid\",\n          \"value\": \"1234-1234-1234-1234\"\n        }\n      ],\n      \"data-type\": \"dataset\",\n      \"yop\": \"2010\",\n      \"performance\": [\n        {\n          \"period\": {\n            \"begin-date\": \"2015-01-01\",\n            \"end-date\": \"2015-01-31\"\n          },\n          \"instance\": [\n            {\n              \"metric-type\": \"total-dataset-requests\",\n              \"access-method\": \"regular\",\n              \"count\": 21\n            }\n          ]\n        }\n      ]\n    }\n  ]\n}",
      "language": "json"
    }
  ]
}
[/block]
## Report specification 

The specification can be found in the [COUNTER Spec](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/), and 

## Identifying which metadata properties to include

The [Report Schema is in Github](https://github.com/datacite/sashimi/blob/master/lib/sushi_schema/sushi_usage_schema.json).

## Register usage reports 

Make direct API calls to DataCite Reports API to register usage reports. This is a REST API, more information is available in the [Usage Reports API documentation](doc:usage-reports-api-guide). If the schema of the report sent is not compliant it will be rejected. There’s a status endpoint, which can be used to GET the status of a given report sent (successful, 409/failed, etc)

More resources: 
[MDC Website](https://makedatacount.org/) 
[Usage Reports API ](doc:usage-reports-api-guide)