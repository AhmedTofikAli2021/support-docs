---
title: Consuming views and downloads
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
There are 3 ways to consume data usage. Each of the following APIs provides an endpoint with  usage counts:

1. [EventData API](doc:consuming-citations#1-event-data) 
2. [GraphQL API](doc:consuming-citations#2-graph-ql)
3. [REST API](doc:consuming-citations#3-the-rest-api)


Now that you have submitted all your usage reports you can now start consuming usage data directly from Datacite. You can read more about how to obtain usage data from the Event Data API. 
[block:html]
{
  "html": "<div>\n\n<a style=\"width:100%\"  href=\"https://support.datacite.org/docs/eventdata-guide#section-usage-events\" class=\"btn btn-primary btn-lg btn-block\" role=\"button\" aria-pressed=\"true\">Event Data API Guide.</a>\n\n \n</div>\n"
}
[/block]
Let's look at a simple example. To consume DOI usage we need to call the `events` endpoint and filter by the *DataCite Usage* `source` and the *DOI name*. To filter by DOI name in this case we will use the `DOI` filter. 

```shell
  curl "https://api.test.datacite.org/events?mailto=YOUR_EMAIL_HERE&source-id=datacite-usage&doi=10.5061/dryad.n81g1" 
```

```json
  {
    data: [{
      id: "8a7b0a30-6638-4544-8935-61e42c02fa61",
      type: "events",
      attributes: {
        subj-id: "https://api.test.datacite.org/reports/2018-3-Dash",
        obj-id: "https://doi.org/10.7291/d1q94r",
        message-action: "add",
        source-token: "28276d12-b320-41ba-9272-bb0adc3466ff",
        relation-type-id: "total-dataset-investigations-regular",
        source-id: "datacite-usage",
        total: 3,
        license: "https://creativecommons.org/publicdomain/zero/1.0/",
        occurred-at: "2128-04-09T00:00:00.000Z",
        timestamp: "2018-05-09T13:53:47Z",
        subj: {
          pid: "https://api.test.datacite.org/reports/2018-3-Dash",
          issued: "2128-04-09"
        },
        obj: {}
      }
    }],
    links: {
      self: "https://api.test.datacite.org/events?doi=10.7291%2Fd1q94r&page%5Bnumber%5D=1&page%5Bsize%5D=25&source-id=datacite-usage",
      first: "https://api.test.datacite.org/events?doi=10.7291%2Fd1q94r&page%5Bnumber%5D=1&page%5Bsize%5D=25&source-id=datacite-usage",
      prev: null,
      next: null,
      last: "https://api.test.datacite.org/events?doi=10.7291%2Fd1q94r&page%5Bnumber%5D=1&page%5Bsize%5D=25&source-id=datacite-usage"
    },
    meta: {
      total: 70,
      total-pages: 2,
      page: 1
    }
  }
```

You will retrieve a [JSONAPI response](http://jsonapi.org/recommendations/). The JSONAPI responses have three main objects: `data`, `links` and `meta`. We will focus on the `data` object, as this object contains all the information we want and its provided from the `DataCite Usage` source. There are a few important things to consider. First, the attribute `data`  is an array and contains the metadata for all the usage metrics for the DOI found by the query. Usually, you will find a maximum of 8 events/links per DOI in this array. One for each metric_type and access_method permutation. 

You should now be able to use the EventData Query API to consume Usage Reports-to-DOI events/links.


# How to display usage?

You can display usage in different ways. DataCite has opted for displaying `unique-dataset-unique-investigations` as `views`  and `unique-dataset-unique-request` as `downloads`. For more details on usage displaying please look at DataCite implementation in [DataCite Search](https://support.datacite.org/docs/usage-stats).


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2b953f0-Screenshot_2019-05-27_at_12.13.15.png",
        "Screenshot 2019-05-27 at 12.13.15.png",
        1054,
        1071,
        "#f6f7f7"
      ],
      "caption": "Example from DataCite Search for https://search.datacite.org/works/10.7272/q6rx997g.",
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]
# Next

Now you have learned how to consume DOI usage. In the next section, you call look an example of how the California Digital Library implemented all these new knowledge in the DASH repository.