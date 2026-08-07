---
title: Best Practices for Tombstone Pages
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
DOIs are persistent identifiers (PIDs), which means that they are intended to be a permanent means of identifying and accessing a particular resource. Because of this, a DataCite DOI cannot be deleted. However, there may be infrequent cases where it is not desirable for the item described by a DOI to be available publicly, such as in the case of research retraction. In these cases, it is best practice to still provide a "tombstone page", which is a special type of landing page describing the item that has been removed. Tombstone pages are generally the responsibility of the organization responsible for maintaining the DOI (in other words, a DataCite Client). 

# Best Practices
## Follow best practices for landing pages
In general, the [Best Practices for DOI Landing Pages](doc:landing-pages) still apply. The tombstone page should provide a full bibliographic citation so that users can verify they have found the correct item (or its last resting place). The tombstone page should contain the DOI itself in both a human-readable and machine-readable format. The only exception is that the user does not need to be able to access the item directly from the landing page, since that item has been removed.

## Include a statement of unavailability
It is best to include a statement of unavailability that details the circumstances that led to the current situation. It should be clear to users that the item being described is in fact associated with the DOI they tried to resolve, but that item is now no longer available. Including a reason for the item's removal is helpful for users. 

# Example of a tombstone page
The image below is an example of a tombstone page from PANGAEA.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e72bd36-TombstonePagePANGAEA.png",
        "TombstonePagePANGAEA.png",
        1829,
        820,
        "#e7e3e2"
      ],
      "caption": "PANGAEA tombstone page"
    }
  ]
}
[/block]
This page conforms to best practices for tombstone pages. 
* It contains a full bibliographic citation of the item, so users can confirm they have located the correct item. 
* It includes the DOI displayed as a URL. 
* It gives a reason for the unavailability of the item. 

# Tombestone page FAQ
## When should I create a tombstone page? 
A tombstone page should be created whenever the item a DOI describes is no longer available, for whatever reason. In general, however, it is better to avoid creating a situation in which a DOI's item is removed, if at all possible. This means being very careful not to accidentally create DOIs, or to put safeguards in place so that users of your repository are not able to accidentally create DOIs. Adjusting your workflow to make better use of Draft DOIs could help with such problems. See [DOI States](doc:doi-states) for more information. 

## How do I create a tombstone page? 
1. Update the state of the DOI to be "Registered". DOIs in the "Registered" state are still registered with the global handle server, so they will resolve if someone knows the exact DOI, but they are not indexed in DataCite Search. 
2. Create a tombstone page in the same way you might create a normal landing page. This could be through your repository software platform or content management system. 
3. Update the URL in the metadata of the DOI to point at the tombstone page you have made. 

## What if I am unable to create a tombstone page? 
Your repository software platform may have a way to help you create tombstone pages, or you may be able to create such pages with the help of your institution's IT department, so you should explore these options first. A tombstone page specific to the removed item is more helpful for users discovering your content. 

In the unlikely situation where the content of a DOI is no longer available and the responsible DataCite Client or Provider does not have the resources to create an appropriately specific tombstone page, they may instead update the DOI metadata for the removed item to point to this generic tombstone URL:

[https://www.datacite.org/invalid.html](https://www.datacite.org/invalid.html)

DataCite does not currently provide any tombstone pages automatically.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]