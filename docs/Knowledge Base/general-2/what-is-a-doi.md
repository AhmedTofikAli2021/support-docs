---
title: What is a DOI?
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
DOI is an acronym for “digital object identifier." DOIs are a type of Persistent Identifier (PID) that uniquely identify digital research content. They are intended to be a permanent way of identifying and accessing a particular resource. DOIs form a persistent link that points to the repository or other digital location by including the URL in the metadata. This provides a system for persistent and actionable identification and interoperable exchange. DOIs remain fixed, but the location and other metadata may change. DataCite DOIs come with a metadata schema that includes a controlled vocabulary of different resource types to describe the content being shared. DataCite members are responsible for updating and managing their DOIs and metadata. DataCite provides a number of services around DOI registration to maximize the benefits of DOI use. Read more about DOIs in [DOI Basics](doc:doi-basics).

##Prefixes

A DOI prefix always starts with '10.' and continues with a number (e.g. '10.1234' or '10.20865'). The DOI prefix is used as a namespace so that DOIs are globally unique. Each Repository account must have a prefix to register DOIs.

##Suffixes

A DOI suffix must be unique within each prefix. The optimum length of a DOI suffix is 6–10 characters. This is long enough to ensure uniqueness, but short enough to avoid typing or text wrapping errors. The DataCite system will not accept DOIs longer than 255 characters.The easiest and recommended option is to use a randomly generated suffix. The auto-generated DOI strings use a-z, 0-9. They avoid i, l, o as they are easily mixed up with 0, 1. We group the suffix into blocks of 4, separated by a hyphen.
[block:callout]
{
  "type": "info",
  "body": "**The auto-generate DOI name functionality means the DOI suffix is generated automatically and will look something like this 10.15138/33bv-s284.**",
  "title": "Auto-generate a suffix"
}
[/block]