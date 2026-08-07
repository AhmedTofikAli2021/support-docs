---
title: DataCite Usage Tracker (beta)
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
> With this early release, we remain committed to refining our processes and aligning with community best practices. Collaborating closely with COUNTER, we eagerly invite input and feedback from the community on this initial iteration. Your valuable insights will help us further develop and enhance the DataCite Usage Tracker. Please get in touch with us at [support@datacite.org](mailto:support@datacite.org) with any feedback or questions.

## How it works

### Processing views and downloads

The DataCite Usage Tracker is based on a custom tracking script that can be included in web pages. When a landing or download page is visited, this tracking script fires an event to the analytics service hosted at DataCite.

### Contributing views and downloads

At the end of each month, DataCite processes these events to generate a usage report, which is submitted to the [DataCite Usage Reports API](https://support.datacite.org/docs/usage-reports-api-guide).

### Consuming views and downloads

When you implement the DataCite Usage Tracker, the resulting usage metrics are exposed through DataCite Commons and our APIs. For more information, see [Consuming Views and Downloads](doc:consuming).

## Setup

### Tracking script

The tracking script is publicly available on GitHub: <https://github.com/datacite/datacite-tracker/>. The source code is there for privacy checking; details of what is sent are easily visible.

To implement the usage tracker, the script is included on DOI landing pages. For example:

```html
<!-- Track View -->
<script defer data-doi="10.5072/1234"
        data-repoid="example.com"
        data-metric=”view”
        src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>

<!-- Track Download -->
<script defer data-doi="10.5072/1234"
        data-repoid="example.com"
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
> The data-repoid is different from your Repository Account ID. If you're interested in implementing the DataCite Usage Tracker during this early release phase, please contact [support@datacite.org](mailto:support@datacite.org) to get your data-repoid.

### View tracking guidelines

The script can be embedded on a landing page:

```html
<script defer data-doi="10.70102/mdc.jeopardy"
	data-repoid="da-1a2b34"
	data-metric="view"
	data-endpoint="https://analytics.datacite.org” src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>
```

### Download tracking guidelines

The script can be embedded on a confirmation page that confirms the download has completed successfully:

```html
<script defer data-doi="10.70102/mdc.jeopardy"
        data-repoid="da-1a2b34"
        data-metric="download"
        src="https://cdn.jsdelivr.net/npm/@datacite/datacite-tracker"></script>
```

If your repository does not have download confirmation pages, setting the data-autotrack option to “false” allows events to be logged from elements on the page.

## Testing

Once the script is installed, events should be tracked on the appropriate page loads: the landing page for views, and the download page for downloads.

To check the script has been installed successfully and DataCite is receiving events, you can query the API to a check endpoint with the data-repoid. This will return the last event tracked date or a message indicating no events have been recorded.

Example call (can be made in a browser):  
[\<https://analytics.datacite.org/api/check/da-1a2b34>](https://analytics.datacite.org/api/check/da-1a2b34)

> 📘 
> 
> Please contact [support@datacite.org](mailto:support@datacite.org) with any questions, feedback, or issues you encounter when implementing the usage tracker.