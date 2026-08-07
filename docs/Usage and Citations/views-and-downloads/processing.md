---
title: Processing views and downloads
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
[block:callout]
{
  "type": "info",
  "body": "This is a summary of subsection 3.3 from the Code of Practice; please refer to this subsection for further details.",
  "title": "Counter Code of Practice"
}
[/block]
When looking at your raw logs, there is certain information you need to consider. First, only successful requests (HTTP status codes 200 and 304) should be counted. Second, make sure the set of minimal fields is present in your logs.

Set of minimal fields:

1. Date and time
2. Request IP address
3. Session cookie ID: an ID kept in a session cookie which only lives as long as the browser/session is open
3. User cookie ID: an ID that identifies a user session that may persist past the closing of the browser window to future visits
4. Username or user ID: identifies a user of the system because they have logged in or identified themselves
5. The requested URL
6. The DOI name. The DOI Identifier which uniquely identifies this dataset
7. The size of the dataset. Size (only needed for requests which download a dataset and not for investigations which display landing pages or metadata about a dataset)
8. The user-agent string being sent by the client

## Log Processing and Enrichment

Your logs processing implementation will need to further process logs that contain the minimal fields as well as enrich such logs. How can one achieve that?

### Classifying logged URLs as either an investigation or a request

First, the logs processing implementation will need to classify logs between `investigations` and `requests.` For example, the  [Counter-Processor](https://github.com/CDLUC3/counter-processor) from CDL does this by way of regular expressions that check against the URL path. ( See the Counter CoP section 3.3.4 "Metric Types").

### Classifying the User as a Robot or Not by the User-Agent

Next,  your implementation will need to classify the logs between those produces by robots or humans. You can achieve that by comparing the user-agent in the logs against the official list of [robots and machines from the MDC project](https://github.com/atmire/COUNTER-Robots). For example, the  [Counter-Processor](https://github.com/CDLUC3/counter-processor) from CDL divides this existing list into [robots](https://github.com/CDLUC3/Make-Data-Count/blob/master/user-agents/lists/robot.txt) and [machine agents](https://github.com/CDLUC3/Make-Data-Count/blob/master/user-agents/lists/machine.txt) lists [in a Github repository](https://github.com/CDLUC3/Make-Data-Count/tree/master/user-agents/lists). There is one text file for robots and one text file for machine agents. These lists are regular expressions separated by newlines in each text file. The Counter Processor retrieves these lists and uses them to classify log lines by the user-agent in each line.



### Obtaining Country-Code for IP addresses

Although not mandatory, you can enrich your logs with country codes to enable more granularity.  For example, the  Counter Processor uses a service called [freegeoip.net](http://freegeoip.net/) for IP to location lookups.  It is free, has the code available on GitHub, is community supported and allows a generous number of API calls per hour (10,000) to their already existing API server. This service provides country, state, and often city/locality IP address geolocation. 

### Generating a Session ID

The CoP has several rules for tracking user-sessions which don't match up with traditional sessions in a web application or web application framework, though they may include those concepts in their session calculation.

The [CoP section 7.2](https://www.projectcounter.org/code-of-practice-rd-sections/7-processing-rules-underlying-reporting-data/
) identifies ways to eliminate double-clicks for the same URL by the same user-session within 30 seconds.  Similarly, the CoP seeks to identify unique dataset visits and unique dataset volume.  The uniqueness identifier is described in the [CoP section 7.3](https://www.projectcounter.org/code-of-practice-rd-sections/7-processing-rules-underlying-reporting-data/
) and is similar, though slightly different than the double-click identification.

### Enriching with DOI Metadata

Finally, you will need to enrich your logs with DOI metadata. The CoP requires submitting descriptive metadata along with statistics for datasets. The descriptive metadata may either be logged at the time a dataset is accessed or have metadata enrichment take place as part of the log processing before making usage counts data available.  The list below contains the mandatory DOI metadata fields that would need to include:

- title
- publisher
- publisher Id
- creators
- publication date
- version of dataset
- URL
- publication year

You can obtain all these metadata by querying the [DataCite API](https://api.datacite.org/dois/) `/dois` endpoint.


For specifics about the logging format CDL is using and that works with the [counter-processor](https://github.com/CDLUC3/counter-processor), please see the [readme](https://github.com/CDLUC3/counter-processor/blob/master/README.md) and [sample log](https://github.com/CDLUC3/counter-processor/blob/master/sample_logs/counter_2018-05-08.log) in that Github repository.