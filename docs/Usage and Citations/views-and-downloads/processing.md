---
title: Processing Views and Downloads
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
## Minimal log information

> 📘 COUNTER Code of Practice
> 
> This is a summary of subsections of the [COUNTER Code of Practice for Research Data](https://www.projectcounter.org/code-of-practice-rd-sections/foreword/) (COUNTER CoP for RD).

When looking at your raw logs, there is certain information you need to consider. First, only successful requests (HTTP status codes 200 and 304) should be counted. Second, make sure the set of minimal fields is present in your logs.

Set of minimal fields:

1. Date and time
2. Request IP address
3. Session cookie ID: an ID kept in a session cookie which only lives as long as the browser/session is open
4. User cookie ID: an ID that identifies a user session that may persist past the closing of the browser window to future visits
5. Username or user ID: identifies a user of the system because they have logged in or identified themselves
6. The requested URL
7. The DOI name: the DOI which uniquely identifies this dataset
8. The size of the dataset: size (only needed for requests which download a dataset and not for investigations which display landing pages or metadata about a dataset)
9. The user-agent string being sent by the client

## Log Processing and Enrichment

Your logs processing implementation will need to further process logs that contain the minimal fields as well as enrich such logs.

### Classify logged URLs as either an investigation or a request

First, the logs processing implementation will need to classify logs between `investigations` and `requests.` For example, the [Counter Processor](https://github.com/CDLUC3/counter-processor) from CDL does this by way of regular expressions that check against the URL path. (See [COUNTER CoP for RD section 3.3.4: Metric Types](https://www.projectcounter.org/code-of-practice-rd-sections/3-technical-specifications-reports/)).

### Classify the User as a Robot or Not by the User-Agent

Your implementation will need to classify the logs between those produced by robots or humans. You can achieve this by comparing the user-agent in the logs against the official list of [robots and machines from the MDC project](https://github.com/atmire/COUNTER-Robots). For example, the [Counter Processor](https://github.com/CDLUC3/counter-processor) from CDL divides this existing list into [robots](https://github.com/CDLUC3/Make-Data-Count/blob/master/user-agents/lists/robot.txt) and [machine agents](https://github.com/CDLUC3/Make-Data-Count/blob/master/user-agents/lists/machine.txt) lists (available in the [Make-Data-Count GitHub repository](https://github.com/CDLUC3/Make-Data-Count/tree/master/user-agents/lists). There is one text file for robots and one text file for machine agents. These lists are regular expressions separated by newlines in each text file. The Counter Processor retrieves these lists and uses them to classify log lines by the user-agent in each line.

### Obtain Country-Code for IP addresses

Although not mandatory, you can enrich your logs with country codes to enable more granularity.  For example, the Counter Processor uses a service called [freegeoip.net](http://freegeoip.net/) for IP to location lookups.  It is free, has the code available on GitHub, is community supported and allows a generous number of API calls per hour (10,000) to their already existing API server. This service provides country, state, and often city/locality IP address geolocation. 

### Generate a Session ID

The COUNTER CoP for RD has several rules for tracking user-sessions which don't match up with traditional sessions in a web application or web application framework, though they may include those concepts in their session calculation.

[COUNTER CoP for RD section 7.2: Double-click Filtering](https://www.projectcounter.org/code-of-practice-rd-sections/7-processing-rules-underlying-reporting-data/#doubleclick_filtering) identifies ways to eliminate double-clicks for the same URL by the same user-session within 30 seconds. Similarly, the COUNTER CoP for RD seeks to identify unique dataset visits and unique dataset volume. The unique identifier is described in [COUNTER CoP for RD section 7.3: Counting Unique Datasets](https://www.projectcounter.org/code-of-practice-rd-sections/7-processing-rules-underlying-reporting-data/#counting_datasets) and is similar to the double-click identification.

### Enrich with DOI Metadata

Finally, you will need to enrich your logs with DOI metadata. The COUNTER CoP for RD requires submitting descriptive metadata along with statistics for datasets. The descriptive metadata may either be logged at the time a dataset is accessed or metadata enrichment may take place as part of the log processing. The list below contains the mandatory DOI metadata fields that should be included:

- dataset title
- publisher
- publisher ID
- creators
- publication date
- dataset version
- URL
- publication year

This metadata can be obtained by querying the the DataCite REST API (see [Retrieving a single DOI](doc:api-get-doi)).

You can also validate your reports against the [JSON schema version of the COUNTER Code of Practice](https://github.com/datacite/sashimi/blob/master/lib/sushi_schema/sushi_usage_schema.json).

For specifics about the logging format used by the Counter Processor from CDL, please see the [README](https://github.com/CDLUC3/counter-processor/blob/master/README.md) and [sample log](https://github.com/CDLUC3/counter-processor/blob/master/sample_logs/counter_2018-05-08.log) in the [Counter Processor](https://github.com/CDLUC3/counter-processor) GitHub repository.