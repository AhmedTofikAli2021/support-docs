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
The DataCite Usage Reports API allows repositories to store data usage metrics. The API requires authentication for most writing endpoints, but all reading endpoints are accessible without credentials. The API is documented in the [Usage Reports API Reference](ref:reports-1).

## Authentication

All requests to the Usage Reports API require authentication for writing. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Usage Reports uses [JWT authentication](https://en.wikipedia.org/wiki/JSON_Web_Token). 

To start interacting with our DataCite Usage Reports API, you must be a DataCite Member. DataCite will provide you a JSON Web Token (JWT). Please contact [support@datacite.org](mailto:support@datacite.org) to obtain a JWT.

> 📘 JSON Web Tokens will expire one year after the date that they are created
> 
> We suggest you request and implement a new token before the previous token expires to maintain continuous access to the Usage Reports API.

## Usage

The DataCite Usage Reports API can be used directly by making HTTP requests with packages such as [cURL](https://curl.haxx.se/docs/manpage.html).

> 🚧 JWT needs to be put in quotes
> 
> If you are using the command line, remember to put your JWT in quotes.

## Fetch Usage Reports

Start by testing our setup. In this guide, the examples we will use would employ the _Usage Reports API Production endpoint_ (i.e., <https://api.datacite.org> ) We will use the curl command-line tool. 

Now, open up a command prompt and enter the following command:

```shell
# GET /reports
curl "https://api.datacite.org/reports/"
```

The response will be a list of all the reports. In this list only the headers of the reports is included. In the next step, we will look at how to see the whole content of each report.

Next, fetch a single usage report:

```shell
# GET /reports/report-id
curl "https://api.datacite.org/reports/21fd2e8e-5481-4bbd-b2ef-742d8b270a66"
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

The response is a usage report in JSON format. We have truncated the report here to save space. The API expects SUSHI-formatted reports in ingestion and returns collections of SUSHI reports for consumption. The API closely follows the [RESEARCH_DATA_SUSHI specification](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/).

Add the `-i` flag to include headers:

```shell
# GET /reports/report-id
curl -i "https://api.datacite.org/reports/21fd2e8e-5481-4bbd-b2ef-742d8b270a66"
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

To register a usage report, you will need to generate a usage report following the [Code of Practice for Research Data Usage Metrics](https://www.projectcounter.org/counter-code-practice-research-data-usage-metrics-release-1/).

> 🚧 
> 
> Usage reports must only contain DOI usage data for a single reporting month. Usage data for successive reporting periods must be submitted in separate usage reports. Usage reports can contain usage data for one or more DOIs.

Once you have your usage report formatted, there are two ways to register a report:

A) using an autogenerated report ID  
B) providing a report ID

To register a usage report with an autogenerated ID, use:

```shell
# POST /reports
curl --header "Content-Type: application/json; Accept: application/json" -H "Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X POST https://api.datacite.org/reports/ -d @usage-report-file.json
```

The successful response will generate a report with an autogenerated report ID that has the form of a UUID. If a report has already been submitted with a matching `created-by` and `reporting-period.begin-date` in the `report-header`, the existing report will be returned. 

To register a usage report with a specific ID, you will need to provide the report ID. The report ID must be a [UUID](https://en.wikipedia.org/wiki/Universally_unique_identifier).

```shell
# PUT /reports/report-id
curl --header "Content-Type: application/json; Accept: application/json" -H "Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X PUT https://api.datacite.org/reports/{report-id-as-uuid} -d @usage-report-file.json
```

The successful response to either call will return the same usage report. The response status can be one of: 

- `201 Created`: Operation successful
- `401 Bad Request`: Invalid JSON
- `401 Unauthorised`: JWT is not provided
- `403 Forbidden`: The provided JWT may be expired
- `415 Wrong Content-Type`: The correct content type may not be included in the header
- `422 Unprocessable Entity`: Invalid JSON, and others

Once you have registered the report, you can fetch the report described earlier in this guide. You can also update the report.

## Update a Usage Report

To update the usage report, provide the report ID of the report you want to update. For example:

```shell
# PUT /reports/report-id
curl --header "Content-Type: application/json; Accept: application/json" -H "Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X PUT https://api.datacite.org/reports/{report-id-as-uuid} -d @usage-report-file.json
```

## Register a large Usage Report

Usage reports can get very large, so there are two ways to approach the submission of very large reports: **compression** and **subsetting**. Large reports need to be divided and compressed. We have set up a top limit of 50,000 datasets per report.

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

### Send compressed reports

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

Compressed reports must be sent using `application/gzip` as _Content Type_ and `gzip` as _Content Encoding_. For example:

```ruby
URI = 'https://api.datacite.org/reports'

def post_file file
  
  headers = {
    content_type: "application/gzip",
    content_encoding: 'gzip',
    accept: 'application/json'
  }
  
  body = compress(file)

  request = Maremma.post(URI, data: body,
    bearer: ENV['TOKEN'],
    headers: headers,
    timeout: 100)
end
```

The equivalent curl call would be:

```shell
curl --header "Content-Type: application/gzip; Content-Encoding: gzip" -H "Authorization: Bearer {YOUR-JSON-WEB-TOKEN}" -X POST https://api.datacite.org/reports/ -d @usage-report-compressed
```

### Send Usage Report in subsets

In order to create a report with more than 50,000 records, keep making POST requests with the same report-header. This will create subsets of the report. For example:

```shell
POST /reports
POST /reports
POST /reports
```

To update an existing compressed report, make a PUT request followed with as many POST requests with the same report-header as needed. For example: 

```shell
PUT /reports/{report-id}
POST /reports
POST /reports
```

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas, please [contact us](doc:how-to-contact-datacite).