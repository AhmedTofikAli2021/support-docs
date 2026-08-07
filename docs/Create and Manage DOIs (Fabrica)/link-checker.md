---
title: Link Checker
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
The DataCite link checker service is a custom-built web crawler that periodically checks a random sampling of DOIs to verify that they still resolve to a valid URL and to gather other useful information about the metadata for DOIs registered with DataCite. 

# How do I use the link checker?
The link checker is a service available only to DataCite Members. The link checker service runs automatically in the background, so there is nothing Members need to do and nothing they need to enable in order to benefit from the service. 

The results of the link checker are displayed in [DOI Fabrica](https://doi.datacite.org) at the bottom of each DOI record that has been checked. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb29e2b-Screenshot_2018-12-18_at_14.51.52.png",
        "Screenshot 2018-12-18 at 14.51.52.png",
        785,
        431,
        "#f5f6f7"
      ]
    }
  ]
}
[/block]
You can filter the list of DOIs on the DOIs tab by HTTP status code to see which DOIs have link checker results of each status. 

Link checker results are also available to DataCite Members via the [REST API](doc:api). 

# How does the link checker work?  
The link checker checks one random DOI per Client per day. It attempts to follow the URL listed in the URL field of the DOI's metadata and returns results about whether it was successful and what it found at the other end. 

The crawler that powers link checker was built open-source by DataCite and goes by the name [PidCheck](http://github.com/datacite/pidcheck). It is software built on top of existing crawler technology, namely the [Scrapy project](https://scrapy.org/), with various customizations specific to us.

# What does the link checker look for? 
The link checker looks for characteristics of proper functioning of URLs, as well as elements that make up a well-formed DOI landing page. (See [Best Practices for DOI Landing Pages](doc:landing-pages).)

## HTTP status code
The link checker will attempt to follow the URL listed in the URL field of the DOI's metadata. If that URL resolves successfully, the link checker will return HTTP status code 200. Otherwise, one of several standard HTTP error codes will be returned, such as 404 (page not found). 

## Number and URL of any redirects
If the link checker is redirected while attempting to follow a URL, the results will display a list of all URLs the link checker was redirected through, ending in the final URL that was ultimately resolved. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47b6e2d-Screenshot_2018-12-19_at_12.44.17.png",
        "Screenshot 2018-12-19 at 12.44.17.png",
        771,
        425,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
## Landing page
The link checker will return the HTTP content type of the content found at the URL to which it ultimately resolves. Ideally, this will be the content type `text/html`, indicating that an HTML landing page was found on the other end. If another content type is found, the link checker will indicate which content type was found.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b48c5f9-Screenshot_2018-12-18_at_15.37.57.png",
        "Screenshot 2018-12-18 at 15.37.57.png",
        770,
        404,
        "#f7f6f4"
      ]
    }
  ]
}
[/block]
## Machine-readable DOI
The link checker will indicate whether a machine-readable DOI was found on the landing page. A "machine-readable DOI" means a DOI that appears in the body of the landing page and is appropriately tagged so as to be recognizable as a DOI by a machine. The link checker looks for either a `DC.identifier` meta tag, a `citation_doi` meta tag, or for appropriately tagged schema.org DOI metadata. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/289bb59-Screenshot_2018-12-19_at_12.49.30.png",
        "Screenshot 2018-12-19 at 12.49.30.png",
        819,
        375,
        "#f7f7f6"
      ]
    }
  ]
}
[/block]
## Schema.org metadata
The link checker looks for schema.org metadata on the landing page, if a landing page is found. It's is specifically looking for embedded JSON-LD with @context `https://schema.org`. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9932ad1-Screenshot_2018-12-19_at_12.50.44.png",
        "Screenshot 2018-12-19 at 12.50.44.png",
        831,
        477,
        "#f7f6f5"
      ]
    }
  ]
}
[/block]
# What do I do if the link checker isn't getting the results I think it should get?
Certain HTTP errors can be temporary. If one of your DOIs is showing that it returned an error code on its last check, try to resolve the URL yourself to see if there is still a problem. If the URL resolves normally, there is no need to contact us. The HTTP status code will be updated the next time the link checker works its way around checking that DOI. 

If the URL resolved successfully (status code 200), but the results of the metadata checks don't align with what you were expecting, make sure that your DOI's landing page conforms to our recommendations for [Best Practices for DOI Landing Pages](doc:landing-pages). If your landing page does conform, but the link checker is not picking up the appropriate results, please contact us at [support@datacite.org](mailto:support@datacite.org) and we will investigate the issue.