---
title: Best Practices for DOI Landing Pages
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
To enable easy usability for both humans and machines, a DOI should resolve to a landing page that contains information about the DOI being resolved. It is the responsibility of the entity creating the DOI to provide such a landing page. The following are best practices for creating well-formed DOI landing pages. 

# Best Practices

## DOIs should resolve to a landing page, not directly to the content

It is important that both humans and machines have context for the item that the DOI is resolving to. DOIs should therefore resolve to a landing page containing metadata about the item, rather than to a PDF, for example. The landing page should contain a full bibliographic citation, so that a human can tell they have arrived at the correct item, and so that a machine can retrieve additional information about the item that might not be easily retrievable from the item itself.  

## The DOI should be displayed on the landing page (so humans can read it)

Humans that follow a DOI link to your landing page should be able to get all information necessary for identifying and citing the item, including the DOI itself, displayed as a URL. This helps to confirm that the item they have found matches the item they were trying to find, and it contributes to creating a well-formed citation.

## The DOI should be appropriately tagged (so that machines can read it)

Even if your DOI is displayed on the landing page, a machine might not be able to tell that this particular string of characters is a DOI without having some additional indicators. You can tag a DOI in several ways, such as by using a `DC.identifier` meta tag, a `citation_doi` meta tag, or by including appropriately tagged schema.org metadata. 

## The landing page should provide a way to access the item

Humans should be able to reach the item being described from the landing page. If the item has been removed, retracted, or otherwise made unavailable to the public on purpose, the landing page should serve as a "tombstone page", providing enough information that the item can be identified and confirmed to have existed at one time. For more information, see our support documentation on [Tombstone Pages](doc:tombstone-pages).

# Example

The image below is an example of a landing page from PANGAEA. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e1e53df-LandingPagePANGAEAwithPageSource.png",
        "LandingPagePANGAEAwithPageSource.png",
        1999
      ],
      "align": "center",
      "caption": "PANGAEA landing page"
    }
  ]
}
[/block]


This page conforms to best practices for landing pages. 

- It contains a full bibliographic citation of the item, so users can confirm they have located the correct item. 
- It includes the DOI displayed as a URL. 
- It provides a way to access the data. 
- The DOI is appropriately tagged in the code for the page.

There is further detailed information about landing pages in [A data citation roadmap for scholarly data repositories](https://www.nature.com/articles/s41597-019-0031-8).

> 📘 What if there are access restrictions on the content being shared on the landing page?
> 
> DataCite's [DOI registration policy](doc:doi-registration-policy) states that: 
> 
> _DOIs must resolve to a publicly available landing page. The underlying content does not need to be publicly available but the metadata must be open._
> 
> A landing page can include data that cannot be accessed, for example, for privacy reasons. However, all DataCite metadata will be made openly available with a CC0 license in line with the DOI registration policy.

> 📘 Can I get started with DOI registration before I have implemented landing pages?
> 
> If you are in the process of implementing landing pages, it is acceptable to _temporarily_ have your DOIs resolve directly to the content (e.g., a PDF file).