---
title: Can I use the DataCite test environment to test the Usage Tracker?
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
The [DataCite Usage Tracker](https://support.datacite.org/docs/datacite-usage-tracker) is a solution for repositories seeking to monitor web-based usage (views and downloads) for their resources. The Usage Tracker automatically logs usage events, forwards them to DataCite and generates usage reports.

To implement the Usage Tracker you will need:

- The custom tracking script included in your web pages
- A data-repoid (send a request to [support@datacite.org](mailto:support@datacite.org))

> 🚧 The Usage Tracker is for production DOIs only and does not work in the DataCite [test system.](https://support.datacite.org/docs/testing-guide)

If you want to check the script has been installed successfully and that DataCite is receiving view and download events, we recommend you start by implementing the Usage Tracker for a single DOI or a small selection of DOIs. You can then query a check API endpoint with the data-repoid: <https://analytics.datacite.org/api/check/{data-repoid}> This will return the last event tracked date or a message indicating no events have been recorded.

When you implement the DataCite Usage Tracker, the resulting usage metrics are exposed through [DataCite Commons](https://commons.datacite.org/repositories/8orcn81) and our APIs.

All DataCite Members registering DOIs can request a data-repoid and set up the script on their landing pages. If you are working with a [service provider](https://support.datacite.org/docs/service-provider-software-integrations), please contact them directly about setting this up on your landing pages.

The [Usage Tracker guide](https://support.datacite.org/docs/datacite-usage-tracker) provides detailed information about how to get started.