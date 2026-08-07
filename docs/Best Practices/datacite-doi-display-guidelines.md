---
title: DataCite DOI Display Guidelines
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
The DataCite DOI Display Guidelines provide a common set of principles that make DataCite DOIs easy to recognize and use, for both researchers and machines.
[block:api-header]
{
  "title": "Overview"
}
[/block]
DataCite DOI Display Guidelines introduce three important components for displaying a DataCite DOIs. First, we have dropped `dx` from the domain name portion of our DOI links. Second, we recommend that the DataCite community use secure HTTPS rather than HTTP. Third, we clarify how to handle cases in DOI names.

For consistency and usability, it is important that all DataCite members follow these Guidelines. Note the Guidelines are for displaying DataCite DOIs. Crossref has developed similar [guidelines](https://www.crossref.org/display-guidelines/), and both organizations’ guidelines are aligned with the IDF (International DOI Foundation) recommendations. 

For the Guidelines to be successful DataCite members must follow these Guidelines and display DataCite DOIs in a consistent manner.
[block:api-header]
{
  "title": "Goals"
}
[/block]
There are three main goals associated with the DataCite DOI Display Guidelines: 
* enable robots and crawlers to recognize DataCite DOIs as URLs
* make it as easy as possible for users to cut, paste or click a link  to share DataCite DOIs (e.g. using right click to copy a URL)
* help users recognize that DataCite DOIs are both a persistent link and a persistent identifier, even if they are unfamiliar with DOIs
[block:api-header]
{
  "title": "Overview of changes to DataCite’s current practices"
}
[/block]
Our new Guidelines introduce three important changes that differ from previous practices:
* drop the `dx` from the domain name portion of DOI links
* use the secure HTTPS rather than HTTP
* allow the use of lowercase letters in DOI names 

Note this change is backward compatible, therefore http://dx.doi.org/ and http://doi.org/ will work indefinitely.
[block:api-header]
{
  "title": "Display DataCite DOIs as a complete link"
}
[/block]
DataCite DOIs should always be displayed as a complete URL using the form: 
[block:code]
{
  "codes": [
    {
      "code": "https://doi.org/10.7939/r3qz22k64",
      "language": "text"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Applying the Guidelines"
}
[/block]
DataCite DOIs should be displayed in the full URL when bibliographic information about content is displayed. DataCite encourages all members to display DataCite DOIs on members’ landing pages. We also recommend that DataCite DOIs be displayed or distributed anywhere users are directed to a permanent, stable, or persistent link to the content including: 
* abstracts
* tables of contents
* full-text HTML and PDF articles, and other scholarly documents
* citation downloads to reference management systems
* metadata feeds to third parties
* “How to Cite This” instructions 
* social media links
[block:api-header]
{
  "title": "DataCite DOIs in Reference Lists"
}
[/block]
DataCite recommends the use of a DataCite DOI URL as a permanent link in reference lists, and we encourage style guides to update their recommendations for DOIs to use the full URL form:
[block:code]
{
  "codes": [
    {
      "code": "Woodward, C. A., Shulmeister, J., Larsen, J., Jacobsen, G. E., \n& Zawadzki, A. (2014). Data from: The hydrological legacy of \ndeforestation on global wetlands (Version 1) [Data set]. Dryad \nDigital Repository. https://doi.org/10.5061/dryad.m62gj",
      "language": "text"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "DOIs, URLs, and Case Sensitivity"
}
[/block]
DOI names **are not** case sensitive, whereas URLs **are** case sensitive. For example, https://doi.org/10.1234/ABC and https://doi.org/10.1234/AbC will be handled as the same DOI. DataCite does not make specific recommendations regarding the case of displayed DOI names, aligned with Crossref and other DOI registration agencies. DataCite expects most DOI names to be displayed in lowercase letters, consistent with how most URLs are used.
[block:api-header]
{
  "title": "Frequently Asked Questions (FAQ)"
}
[/block]
**Do members need to change how DOIs are displayed in already published content?**

No, you can make the change for new content going forward and do not need to update existing content. You can update existing content if you want but this is optional. The current form for DOI links using http://dx.doi.org will continue to work as long as DataCite, and the DOI system exists.

**When will the DataCite DOI Display Guidelines take effect?**

These these Guidelines are effective immediately. 

**Do DataCite DOIs need to be displayed as a link on the page that the DOI links to?**

Yes, a DataCite DOI must be displayed as a link, because it is both an identifier and a persistent link. It is easier for users when a DOI is displayed as a full link as it can be easily copied and reused. Also, many users are more familiar with a link than a DOI and we want to encourage uptake. DOIs should be used as a persistent link and shared and used in other applications (e.g. reference managers). 

**Do DataCite members need to update their metadata to update their URLs?**

No, there is no need to update your metadata. These Guidelines cover how you display DOIs on your website, not how to register them with DataCite.

**Will the IDF’s ShortDOI service continue to work?**

The International DOI Foundation created the ShortDOI service as an open system that creates shortcuts to DOIs and this service will continue to work. The short form of the DOI for https://doi.org/10.5285/1D4D70AD-DC38-4E5F-BC39-066BABCA2FB2 is https://doi:10/bcc7. Alternatively, users can register DOI names with short suffixes such as https://doi.org/10.5438/4k3m-nyvg. 

**Why should members use HTTPS?**

Providing the central linking infrastructure for scholarly content is something DataCite takes seriously. Because we all form the connections between content all over the web, it’s important that the DataCite community does its share to enable secure browsing from start to finish. Also, HTTPS is now a ranking signal for Google who gives sites using HTTPS a small ranking boost.

The process of enabling HTTPS on various member and client sites will take a long time given the number of DataCite members and clients. However, by using HTTPS, we are future-proofing scholarly linking on the web.

**Why not simply use `doi:` or `DOI:` as we have in the past?**

When DataCite was founded, it was common community practice for DOIs to be displayed in the format `doi:10.NNNN/doisuffix`. Many still use `doi:[space][doinumber]`, `DOI: [space][doinumber]`, or `DOI[space][doinumber]`. When the DOI system was launched in the 1990s it was thought that doi: would become native to browsers and automatically resolve DOIs, similar to `HTTP:`, but this never happened. Advantages to changing the display to a resolvable URL - even on the page the DOI itself resolves to - include the following:

* A DOI is both a link and an identifier. Users will more easily recognize DataCite DOIs as an actionable link, regardless of whether they know about DOIs.
* Users who do not know how to right-click on the link and choose “Copy Link,” will be able to copy the DOI URL easily.
* Machines and programs (e.g. bots, etc.) will recognize the DOI as a link, thereby increasing discoverability and usage.

**What about reference formats in style guides (e.g. APA, Chicago) that use `doi: [doinumber]`?**

A number of style guides recommend that the inclusion of DOI in the reference as an unlinked string. We encourage style guides to update their recommendations for DOIs to use the full URL form.

**Why not use `dx` as in http://dx.doi.org/ ?**

Originally the dx separated the DOI resolver from the International DOI Foundation (IDF) website but this changed a few years ago and the IDF recommends http://doi.org as the preferred form for the domain name in DOI URLs.

**Where can we find out more information on DOIs?**

See the IDF’s (the International DOI Foundation) [DOI Handbook](http://www.doi.org/hb.html) for a complete overview of the structure and use of DOIs.
[block:callout]
{
  "type": "info",
  "title": "Would you like to know more?",
  "body": "These guidelines are based on [Crossref's DOI display guidelines](https://www.crossref.org/display-guidelines/). Thanks to Crossref for their input!\n\nIf you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)"
}
[/block]