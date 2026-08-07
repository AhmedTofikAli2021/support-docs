---
title: How do I expose my datasets to Google Dataset Search?
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
Google Dataset Search relies on exposed crawlable structured data via schema.org markup, using the schema.org `dataset` class. DataCite exposes an index of such crawlable data thanks to DataCite Search. 'Dataset' items (according to the `resourceTypeGeneral`) found in DataCite Search will show up in Google Dataset Search with a DOI link, as well as a link to the source record in DataCite Search. The DOI link will resolve to your dataset’s regular landing page. 


If you would like your datasets to also show up in Google Dataset Search with a direct link to your own repository as the source, then you should expose the appropriately crawlable structured data by implementing schema.org markup (using the `dataset` class) on each landing page in your repository. 

One easy way to do this is by enabling our *Content Negotiation Service* in your landing pages. For example, you can include this [javascript file](https://gist.github.com/kjgarza/34ca6a866b4437bc1c07d84f208a01c4) that will return Metadata in schema.org marked-up JSON dynamically through the power of our *Content Negotiation Service*. Just add a `<script></script>` tag with the file to the script to your landing pages template, and whenever that landing page is requested, the script will append the appropriately marked up metadata in schema.org markup. 
[block:callout]
{
  "type": "success",
  "title": "To ensure your datasets will appear in Google Dataset Search:",
  "body": "1. They must have the Findable state (which is what makes them indexable). \n2. They must have `Dataset` as the `resourceTypeGeneral` in the metadata you have registered with DataCite. `Text` items, for example, won't appear in Google Dataset Search.\n\n**If you also want your datasets to appear in Google Dataset Search with a direct link to your repository as the source, you must additionally:**\n3. Implement schema.org markup on your datasets' landing page and use the `dataset` class."
}
[/block]
Google updates the data they show on a regular basis, but their schedule is out of DataCite’s control. As long as your DataCite-registered DOIs are Findable and are tagged as datasets, they will appear in Google Dataset Search once Google has re-indexed. 

For more information on exposing your datasets to Google Dataset Search, see Google's help page on the [Dataset content type](https://developers.google.com/search/docs/data-types/dataset).

If you’re not sure whether your repository landing pages contain the appropriate structured data, you can test them using Google’s [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool).