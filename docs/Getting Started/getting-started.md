---
title: Getting Started
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
##Welcome to DataCite

DataCite is a leading global non-profit organisation that provides persistent identifiers (DOIs specifically) for research data and other research outputs. Organizations within the research community join DataCite as members to be able to assign DOIs to all their research outputs. This way, their outputs become discoverable and associated metadata is made available to the community. DataCite then develops additional services to improve the DOI management experience, making it easier for our members to connect and share their DOIs with the broader research ecosystem and to assess the use of their DOIs within that ecosystem.

DataCite is an active participant in the research community and promotes data sharing and citation through community-building efforts and outreach activities.

Your organization must be a member of DataCite to register DOIs with us. If your organization is interested in joining DataCite please reach out to us by sending an email to [support@datacite.org](mailto:support@datacite.org) and expressing you interest. You can find more information about membership in our [website](https://datacite.org/become.html).

You can also take a look at the [DataCite Brochure](https://datacite.org/assets/DataCite_Brochure.pdf) for comprehensive information about the organization and services.

##Some background on DOIs 

DOI is an acronym for “digital object identifier. DOIs are a type of Persistent Identifier (PID) that uniquely identify digital research content. They are intended to be a permanent way of identifying and accessing a particular resource. DOIs form a persistent link that points to the repository or other digital location by including the URL in the metadata. This provides a system for persistent and actionable identification and interoperable exchange. DOIs remain fixed, but the location and other metadata may change. DataCite DOIs come with a metadata schema that includes a controlled vocabulary of 15 different resource types to describe the content being shared. DataCite members are responsible for updating and managing their DOIs and metadata. DataCite provides a number of services around DOI registrationto maximize the benefits of DOI use. Read more about DOIs in [DOI Basics](doc:doi-basics).

##Managing prefixes and suffixes

A DOI name consists of a prefix and a suffix separated by a forward slash (e.g. **10.1234/56789**). Each organisation is assigned its own unique prefix(es). Each repository needs at least one prefix to register DOIs. This can be assigned by the member organization the repository belongs to. 

A DOI suffix must be unique within each prefix. The optimum length of a DOI suffix is 8–10 characters. This is long enough to ensure uniqueness, but short enough to avoid typing or text wrapping errors. The DataCite system will not accept DOIs longer than 255 characters.
[block:callout]
{
  "type": "info",
  "body": "**The auto-generate DOI name functionality means the DOI suffix is generated automatically and will look something like this 10.15138/33bv-s284.**"
}
[/block]

##Registering your first DOI
 
**To register DOIs you need a [repository environment](dois:create-a-client) and a [prefix](dos:fabrica-assign-prefixes).**

If you are new to DOI registration we recommend you practice registering DOIs in our test environment. The test environment works like a sandbox and nothing you do there will go live. Check out our guide to testing [here](https://support.datacite.org/docs/testing-guide). Once you move into the production environment, we recommend you consider using the "draft" state for DOIs, to avoid a situation where unwanted DOIs are registered.

DOIs can be registered using DataCite's web interface [DOI Fabrica](https://support.datacite.org/docs/doi-fabrica) or one of our APIs. You will find lots of information on the support site including information about [DOI states](https://support.datacite.org/docs/doi-states), [metadata examples](https://support.datacite.org/docs/metadata-examples), and [best practices for landing pages](https://support.datacite.org/docs/landing-pages).

**Watch this short video to learn how to create your first DOI using the form in DOI Fabrica**
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FsyBu-JKYA10%3Ffeature%3Doembed&url=http%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DsyBu-JKYA10&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FsyBu-JKYA10%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=syBu-JKYA10&feature=youtu.be",
  "title": "Creating a DOI using the form in Fabrica",
  "favicon": "https://s.ytimg.com/yts/img/favicon-vfl8qSV2F.ico",
  "image": "https://i.ytimg.com/vi/syBu-JKYA10/hqdefault.jpg"
}
[/block]