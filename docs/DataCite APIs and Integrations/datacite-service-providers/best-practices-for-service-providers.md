---
title: Best Practices for Service Providers
excerpt: Version 2.0, July 2023
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

A Service Provider is an organization that has integrated with one of the DataCite APIs to enable other organizations to register DataCite DOIs. DataCite Registered Service Providers do not offer DOIs, but do offer DataCite Members and Consortium Organizations the ability to register DOIs through their platform. Members and Consortium Organizations register DOIs using their own Repository account credentials.

Participants in the DataCite Registered Service Providers program should make best efforts to adhere to best practices outlined on our support site. The key best practices are summarized in two guides:

## [Best Practices for Integrators](doc:best-practices-for-integrators)

All DataCite Registered Service Providers should follow [Best Practices for Integrators ](doc:best-practices-for-integrators). This guide covers how to work with the DataCite REST API to authenticate with a Repository account, reserve a DOI, register and update DOIs, test your integration, and interpret error codes.

## [Best Practices for DOI Registration](doc:best-practices-for-datacite-members)

All DataCite Registered Service Providers should follow [Best Practices for DOI Registration](doc:best-practices-for-datacite-members), which include guidelines for what a DataCite DOI can be assigned to, forming and displaying DOIs, landing pages, tombstone pages, and DOI states.

## DataCite terminology

The following is terminology used at DataCite that is relevant to Registered Service Providers, and is used throughout our support site.

**Member**: The entity that joins DataCite. This entity is responsible for paying membership fees and has voting representation in DataCite’s governance. There are two types of membership that support DOI registration:

- **Direct Member**: In the DataCite membership model, a Direct Member supports DataCite's research sharing mission and is an organization that works with one or more repositories within their organization. A Direct Member account has permission to create new Repositories and update contact information.
- **Consortium**: In the DataCite membership model, a consortium is a group of organizations within one region or discipline that have come together to collectively participate in DataCite’s community and governance activities and use DataCite’s DOI services. A Consortium Lead account has permission to create and manage Consortium Organization accounts and new Repository accounts as well as contact information .

**Consortium Organization**: A Consortium Organization is part of a DataCite consortium. The Consortium Organization account has permission to create and manage new Repository accounts and update contact information.

**Repository**: Repositories play a key role in the DataCite membership model and are defined as a service operated by research organizations, where research materials are stored, managed and made accessible. A Repository is a single unit. A Repository account represents a store where all the DOIs for a group of resources are registered and will stay together. They have one unique prefix and are used exclusively for DOI registration. A Repository account may belong to a Direct Member or Consortium Organization.

**Prefix**: The beginning numeric portion of a DOI string before the slash. A DOI prefix always starts with '10.' and continues with a number (e.g., '10.1234' or '10.20865'). Each prefix may be associated with one and only one Repository. It is possible for a Repository to have more than one prefix, but DataCite generally recommends a one-to-one relationship between Repositories and prefixes.