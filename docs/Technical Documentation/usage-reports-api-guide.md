---
title: DataCite Usage Reports API Guide
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
## Purpose

The DataCite Usage Reports API allows repositories to store data usage metrics. The API requires authentication for most writing endpoints but all reading endpoints are accessible without credentials. There is a [Live API reference](https://support.datacite.org/reference#usage-reports) also available. To obtain credentials, your repository needs to be a Datacite client. Interested parties should contact the [DataCite support](mailto:support@datacite.org) team. 

## Authentication

All requests to the Usage Reports API require authentication for writing. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Usage Reports uses [JWT authentication](https://en.wikipedia.org/wiki/JSON_Web_Token). 

To start interacting with our DataCite Usage Reports API you must be a DataCite Provider or Client:
* If you are a DataCite Provider, DataCite will provide you a JSON Web Token.
* If you are a DataCite Client, your Provider will provide you a JSON Web Token.
[block:callout]
{
  "type": "warning",
  "title": "JWT needs to be put in quotes",
  "body": "If you are using the command line remember to put your JWT in quotes."
}
[/block]
## How to Use

The DataCite Usage Reports API can be used directly by making HTTP requests with packages such as [cURL](https://curl.haxx.se/docs/manpage.html).

## Fetching Usage Reports

Let's start by testing our setup. In this guide, the examples we will use would employ the *Usage Reports API Production endpoint* (i.e., https://api.datacite.org ) We will use the curl command-line tool. 

Now, open up a command prompt and enter the following command:

```shell
# GET /reports
$ curl  https://api.datacite.org/reports/
```

The response will be a list of all the reports. In this list only the headers of the reports is included. In the next step we will look at how to see the whole content of each report.

Next, let's fetch a single usage report:

```shell
# GET /reports/report-id
$ curl https://api.datacite.org/reports/21fd2e8e-5481-4bbd-b2ef-742d8b270a66
```

```json
{
	"report": {
		"id": "21fd2e8e-5481-4bbd-b2ef-742d8b270a66",
		"report-header": {
			"report-name": "dataset report",
			"report-id": "DSR",
			"release": "rd1",
			"created-by": "Dash",
			"created": "2018-04-30",
			"reporting-period": {
				"end-date": "2018-04-30",
				"begin-date": "2018-04-01"
			},
			"report-filters": [],
			"report-attributes": []
		},
		"report-datasets": [
			{
				"uri": "https://oneshare.cdlib.org/stash/dataset/doi:10.15146/R3J66V",
				"yop": "2017",
				"platform": "Dash",
				"data-type": "dataset",
				"publisher": "DataONE",
				"dataset-id": [
					{
						"type": "doi",
						"value": "10.15146/R3J66V"
					}
				],
				"performance": [
					{
						"period": {
							"end-date": "2018-04-30",
							"begin-date": "2018-04-01"
						},
						"instance": [
							{
								"count": 20,
								"metric-type": "total-dataset-requests",
								"access-method": "regular",
								"country-counts": {
									"au": 6,
									"jp": 1,
									"us": 13
								}
							},
							{
								"count": 5,
								"metric-type": "unique-dataset-requests",
								"access-method": "regular",
								"country-counts": {
									"au": 1,
									"jp": 1,
									"us": 3
								}
							},
							{
								"count": 4,
								"metric-type": "total-dataset-investigations",
								"access-method": "regular",
								"country-counts": {
									"de": 2,
									"dk": 1,
									"us": 1
								}
							},
							{
								"count": 4,
								"metric-type": "unique-dataset-investigations",
								"access-method": "regular",
								"country-counts": {
									"de": 2,
									"dk": 1,
									"us": 1
								}
							},
							{
								"count": 14,
								"metric-type": "total-dataset-requests",
								"access-method": "machine",
								"country-counts": {
									"kr": 14
								}
							},
							{
								"count": 14,
								"metric-type": "unique-dataset-requests",
								"access-method": "machine",
								"country-counts": {
									"kr": 14
								}
							}
						]
					}
				],
				"publisher-id": [
					{
						"type": "grid",
						"value": "tbd"
					}
				],
				"dataset-dates": [
					{
						"type": "pub-date",
						"value": "2017-12-31"
					}
				],
				"dataset-title": "Influence of human disturbance on marine invertebrate biodiversity in Acadia National Park’s rocky intertidal community",
				"dataset-contributors": [
					{
						"type": "name",
						"value": "Cassandra Lopez"
					}
				]
			},
			{
				"uri": "https://dash.ucmerced.edu/stash/dataset/doi:10.6071/M32Q0X",
				"yop": "2017",
				"platform": "Dash",
				"data-type": "dataset",
				"publisher": "UC Merced",
				"dataset-id": [
					{
						"type": "doi",
						"value": "10.6071/M32Q0X"
					}
				],
				"performance": [
					{
						"period": {
							"end-date": "2018-04-30",
							"begin-date": "2018-04-01"
						},
						"instance": [
							{
								"count": 32,
								"metric-type": "total-dataset-requests",
								"access-method": "regular",
								"country-counts": {
									"au": 10,
									"de": 7,
									"dk": 1,
									"us": 14
								}
							},
							{
								"count": 8,
								"metric-type": "unique-dataset-requests",
								"access-method": "regular",
								"country-counts": {
									"au": 3,
									"de": 1,
									"dk": 1,
									"us": 3
								}
							},
							{
								"count": 35,
								"metric-type": "total-dataset-investigations",
								"access-method": "regular",
								"country-counts": {
									"br": 2,
									"de": 4,
									"dk": 1,
									"us": 28
								}
							},
							{
								"count": 27,
								"metric-type": "unique-dataset-investigations",
								"access-method": "regular",
								"country-counts": {
									"br": 2,
									"de": 4,
									"dk": 1,
									"us": 20
								}
							}
						]
					}
				],
				"publisher-id": [
					{
						"type": "grid",
						"value": "266096.d"
					}
				],
				"dataset-dates": [
					{
						"type": "pub-date",
						"value": "2017-09-06"
					}
				],
				"dataset-title": "TWOSTATE, a resonance Raman excitation profile and absorption spectrum simulator",
				"dataset-contributors": [
					{
						"type": "name",
						"value": "Anne Kelley"
					}
				]
			}
		]
	}
}


```
The response is a usage report in json format. We have truncated the report here to save space. The API expects SUSHI-formatted reports in ingestion and returns collections of SUSHI reports for consumption. The API closely follows the [RESEARCH_DATA_SUSHI specification](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/).

Let's add the `-i` flag to include headers:

```shell
# GET /reports/report-id
$ curl -i https://api.datacite.org/reports/21fd2e8e-5481-4bbd-b2ef-742d8b270a66
```

```shell
< HTTP/1.1 200 OK
< Date: Wed, 22 Aug 2018 08:26:05 GMT
< Content-Type: application/json; charset=utf-8
< Transfer-Encoding: chunked
< Connection: keep-alive
< Status: 200 OK
< X-Anonymous-Consumer: true
< Cache-Control: max-age=0, private, must-revalidate
< Vary: Accept-Encoding, Origin
< ETag: W/"cc8c86a0ad0181ac67dcbebb7127f675"
< X-Runtime: 0.267312
< X-Request-Id: 22ede321-a835-43c1-b954-23ac81313fe2
< X-Powered-By: Phusion Passenger 5.3.4
< Server: nginx/1.14.0 + Phusion Passenger 5.3.4

{
	"report": {
		"id": "21fd2e8e-5481-4bbd-b2ef-742d8b270a66",
		"report-header": {
```


## Register a Usage Report

To register a usage report you will need to generate a Data Usage report following the [Code of practice for research data usage metrics](https://peerj.com/preprints/26505/). Additionally, the allowed and recommended characters for a URL-safe naming of parameters are defined in the format spec. To standardize parameter names, the following (more restrictive) rules are recommended:

- Parameter names SHOULD start and end with the characters “a-z” (U+0061 to U+007A)
- Parameter names SHOULD contain only the characters “a-z” (U+0061 to U+007A), “0-9” (U+0030 to U+0039), and the hyphen minus (U+002D HYPHEN-MINUS, “-“) as a separator between multiple words.

There are also a few tools you can use to generate your usage report based on your repository weblogs. For example, the [Counter Processor](https://github.com/CDLUC3/counter-processor) is a Python 3 (written in 3.6.4) script for processing dataset access statistics from logs.

Once you have your usage report formatted, there are two ways to register a report:

A) using an autogenerated report ID
B) providing a report ID


To register a usage report with an autogenerated ID use:

```shell
# POST /reports
$ curl --header "Content-Type: application/json; Accept: application/json" -H "X-Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X POST https://api.datacite.org/reports/ -d @usage-report-file.json
```

The successful response will generate a report with an autogenerated report ID that has the form of a UUID.

To register a usage report with a specific ID you will need to provide the report ID. Keep in mind that the report ID MUST be a [UUID](https://en.wikipedia.org/wiki/Universally_unique_identifier).


```shell
# PUT /reports/report-id
$ curl --header "Content-Type: application/json; Accept: application/json" -H "X-Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X PUT https://api.datacite.org/reports/{report-id-as-uuid} -d @usage-report-file.json
```


The successful response to either call will return the same usage report. The response status can be one of: 

* `201 Created`: operation successful
* `401 Unauthorised`: no JWT provided
* `403 Forbidden`: JWT expired,
* `415 Wrong Content-Type`: Not including the correct content type in the header.
* `422 Unprocessable Entity`: invalid JSON, and others.


Once you have registered the report, you can fetch the report described earlier in this guide. You can also update the report.

## Update a Usage Report

To update the usage report you simply need to provide the report ID of the report you want to update like so:

```shell
# PUT /reports/report-id
$ curl --header "Content-Type: application/json; Accept: application/json" -H "X-Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X PUT https://api.datacite.org/reports/{report-id-as-uuid} -d @usage-report-file.json
```

## Register a large Usage Report

Usage reports can get very large, so we have to ways to approach the submission of very large reports. The first approach is compression and the second is subsetting. Large reports need to be divided and compressed. We have set up a top limit of 50,000 datasets per report.

In both cases, you need to add this exception in the report header:

```json
"exceptions": [{
  "code": 69,
  "severity": "warning",
  "message": "Report is compressed using gzip",
  "help-url": "https://github.com/datacite/sashimi",
  "data": "usage data needs to be uncompressed"
}]
```


### Sending compressed reports

 We suggest compressing any report that is larger than 10MB. Here it is a ruby example of report compression:

```ruby
def compress file
  report = File.read(file)
  gzip = Zlib::GzipWriter.new(StringIO.new)
  string = JSON.parse(report).to_json
  gzip << string
  body = gzip.close.string
  body
end
```
When sending the compressed reports you need to send them using `application/gzip` as *Content Type* and `gzip` as *Content Encoding*. For example

```ruby
URI = 'https://api.datacite.org/reports'

def post_file file
  
  headers = {
    content_type: "application/gzip",
    content_encoding: 'gzip',
    accept: 'gzip'
  }
  
  body = compress(file)

  request = Maremma.post(URI, data: body,
    bearer: ENV['TOKEN'],
    headers: headers,
    timeout: 100)
end
```

The equivalent Curl call would be:

```shell
$ curl --header "Content-Type: application/gzip; Content-Encoding: gzip" -H "X-Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X POST https://api.datacite.org/reports/ -d @usage-report-compressed
```

### Send Usage Report in subsets

In order to create a report with more than 50,000 records, just keep making POST requests with the same report-header. This will create subsets of the report. For example:

```shell
POST /reports
POST /reports
POST /reports
```

To update an existing compressed report make a PUT request followed with as many POST requests with the same report-header as you need. For example: 

```shell
PUT /reports/{report-id}
POST /reports
POST /reports
```

## Next

Now you know the basics of the Usage Reports API!

- Authentication
- Fetching and registering and updating usage reports


Keep learning with the [Usage Reports API Reference](https://support.datacite.org/reference#usage-reports)!
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]