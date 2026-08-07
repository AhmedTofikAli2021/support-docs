---
title: DataCite Usage Tracker
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
The DataCite Usage Tracker, currently in its early release phase, offers a solution for repositories seeking to monitor data usage. The DataCite Usage Tracker aligns with the principles of the [COUNTER Code of Practice for Research Data](https://support.datacite.org/docs/counter-code-of-practice) but eliminates the need for custom log processing. Instead, it automatically logs usage events, forwards them to DataCite, and generates usage reports. Key advantages include:

- **Simple Client-Side Implementation: **Repositories embed a JavaScript tracker in their landing pages that automatically collects usage data and sends it to DataCite.
- **Simplified Reporting:** DataCite’s analytics processing service generates monthly usage reports for repositories from the submitted usage data. Repositories do not need to generate these reports themselves.
- **Privacy-Focused:** Never retains personally identifiable information.

The DataCite Usage Tracker aims to assist repositories in monitoring web-based usage. Repositories interested in also tracking machine/API usage can [set up log processing](doc:processing) and [submit their machine/API usage data](doc:contributing) to DataCite separately.

> 📘 
> 
> We are continuing to develop and enhance the DataCite Usage Tracker based on feedback from early adopters. To help us continue to improve, please get in touch with us at [support@datacite.org](mailto:support@datacite.org) with any feedback or questions.

## How it works

### Processing views and downloads

The DataCite Usage Tracker is based on a custom tracking script that can be included in web pages. When a landing or download page is visited, this tracking script fires an event to the analytics service hosted at DataCite.

> 📘 
> 
> User-Agent data is sent to the analytics service and is used to filter views and downloads by known bots. The User-Agent data is discarded once it is processed and is not stored. Details of what is sent are visible in the source code, available on GitHub: <https://github.com/datacite/datacite-tracker>

### Contributing views and downloads

At the end of each month, DataCite processes these events to generate a usage report, which is submitted to the [DataCite Usage Reports API](https://support.datacite.org/docs/usage-reports-api-guide).

### Consuming views and downloads

When you implement the DataCite Usage Tracker, the resulting usage metrics are exposed through DataCite Commons and our APIs. For more information, see [Consuming Views and Downloads](doc:consuming).

## Setup

### Tracking script

To implement the Usage Tracker, the script is included on DOI landing pages. For example:

```html
<!-- Track View -->
<script defer data-doi="10.5072/1234"
        data-repoid="da-1a2b34"
        data-metric=”view”
        src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>

<!-- Track Download -->
<script defer data-doi="10.5072/1234"
        data-repoid="da-1a2b34"
        data-metric="download"
        src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>
```

The following attributes are configurable:

| Attribute      | Description                                                                                                                                                                                                         |
| :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| data-repoid    | Required. This is the unique identifier for tracking your usage analytics. This will be provided by DataCite; please contact [support@datacite.org](mailto:support@datacite.org).                                   |
| data-metric    | Optional. Must be “view” or “download”. If not provided, defaults to “view”.                                                                                                                                        |
| data-doi       | Optional. The DOI you want to track. The code will scan for the DOI in embedded schema.org or Dublin Core metadata; if this is not available, the DOI must be specified.                                            |
| data-autotrack | Optional. Must be "true" or "false". Advanced usage to stop the auto tracking. This is for manual setup, i.e., custom Javascript calling the trackMetric function as required. If not provided, defaults to “true”. |

> 👍 Get your data-repoid
> 
> The data-repoid is different from your Repository Account ID. If you are interested in implementing the DataCite Usage Tracker during this early release phase, please contact [support@datacite.org](mailto:support@datacite.org) to get your data-repoid.

### View tracking guidelines

The script can be embedded on a landing page:

```html
<script defer data-doi="10.70102/mdc.jeopardy"
	data-repoid="da-1a2b34"
	data-metric="view"
	data-endpoint="https://analytics.datacite.org" src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>
```

### Download tracking guidelines

The script can be embedded on a confirmation page that confirms the download has completed successfully:

```html
<script defer data-doi="10.70102/mdc.jeopardy"
        data-repoid="da-1a2b34"
        data-metric="download"
        src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>
```

If your repository does not have download confirmation pages, setting the data-autotrack option to “false” allows events to be logged from elements on the page:

```html
<script 
        data-autotrack="false" 
        src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker">
</script>
<script>
  const { trackMetric } = DataCiteTracker.Tracker({
    repoId: 'da-1a2b34',
    trackLocalhost: true,
    apiHost: 'https://analytics.datacite.org'
  })
  trackMetric(DataCiteTracker.MetricType.Download, { doi: "10.70102/mdc.jeopardy" })
</script>
```

## Testing

### Confirm that DataCite is receiving view and download events

Once the script is installed, events should be tracked on the appropriate page loads: the landing page for views, and the download page for downloads.

To check the script has been installed successfully and DataCite is receiving events, you can query the API to a check endpoint with the data-repoid. This will return the last event tracked date or a message indicating no events have been recorded.

Example call (can be made in a browser): <https://analytics.datacite.org/api/check/da-1a2b34>

### Review reported views and downloads

Usage data recorded by the Usage Tracker for any given month is available at the beginning of the following month. You can review reported views and downloads using several different methods. 

#### REST API

The simplest way to review views and downloads recorded by the Usage Tracker is using the REST API. To check the views and downloads for a single DOI, send a request to the `/dois` endpoint using the DOI:

```shell
curl  "https://api.datacite.org/dois/10.5068/d1k39s"
```

Usage data by month is available in the `viewsOverTime` and `downloadsOverTime` attributes:

```json
"viewsOverTime": [
  {
    "yearMonth": "2021-01",
    "total": 4
  },
...
```

For more information, see [Consuming Views and Downloads](doc:consuming). 

#### Usage reports

The Usage Tracker generates usage reports that are accessible in the [Usage Reports API](doc:usage-reports-api-guide). To get a list of usage reports generated by your data-repoid, send a request with `da_{Repository Account ID associated with your data-repoid}`. Example request for Repository Account ID `DRYAD.DRYAD`:

```shell
curl "https://api.datacite.org/reports?created_by=da_DRYAD.DRYAD"
```

Once you have the list of generated usage reports, you can [retrieve single usage reports](https://support.datacite.org/docs/usage-reports-api-guide#fetching-usage-reports) using their `id` and then analyze the usage data reported by the Usage Tracker. Reports may be GZIP compressed in the `report.report-subsets.gzip` attribute and will need to be decompressed for analysis. Example request for a single usage report generated by the Usage Tracker:

```shell
curl "https://api.datacite.org/reports/08ac6a6f-45ed-4ade-8f75-0f3d2b56073c"
```

#### Event Data

Usage reports generate [Event Data](doc:eventdata-guide) that can be retrieved with the Event Data API. To check the Event Data associated with a usage report generated by the Usage Tracker, send a request with the Usage Reports API URL in the `subj-id` parameter:

```shell
curl "https://api.datacite.org/events?subj-id=https://api.datacite.org/reports/08ac6a6f-45ed-4ade-8f75-0f3d2b56073c"
```

Alternatively, you can check the usage Event Data associated with a single DOI using the `doi` parameter with the `source-id` parameter set to `datacite-usage`: 

```shell
curl "https://api.datacite.org/events?doi=10.5068/d1k39s&source-id=datacite-usage"
```

Keep in mind that this request will also return usage Event Data for all usage reports submitted by your repository. These may include those submitted using the Usage Reports API in addition to those recorded by the Usage Tracker.

### Testing strategies

We suggest implementing the Usage Tracker using the following strategies:

- Start by implementing the Usage Tracker for a single DOI or a selection of DOIs. 
- Make sure that the API is receiving view and download events using the endpoint described above, e.g. `https://analytics.datacite.org/api/check/{data-repoid}`.
- Allow the Usage Tracker to report usage events for a full month. 
- At the beginning of the following month, confirm that views and downloads are being sent correctly using the review methods described above.

> 📘 
> 
> The Usage Tracker won't work for test DOIs created in the [test system](doc:testing-guide).

> 📘 
> 
> In technical environments where a Javascript embed is not suitable, alternatives include: 
> 
> 1. Log processing by contributing usage reports with the [Usage Reports API](doc:usage-reports-api-guide).
> 2. Submitting usage events to the [Usage Tracker API](https://support.datacite.org/reference/usage-tracker).

> 📘 
> 
> Please contact [support@datacite.org](mailto:support@datacite.org) with any questions, feedback, or issues you encounter when implementing the Usage Tracker.