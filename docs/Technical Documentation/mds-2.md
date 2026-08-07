---
title: Metadata Store (MDS) API Guide
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
## Purpose of the DataCite Metadata Store (MDS) API

The [DataCite Metadata Store (MDS) API](https://datacite.readme.io/v1.0/reference#overview) allows users to register DataCite DOIs and associated metadata. The API works as a REST API and requires authentication. To retrieve DOI metadata records users should use our [DataCite REST API](api.datacite.org). To become a member, interested parties should contact the [DataCite support](mailto:support@datacite.org) team. The [DataCite Metadata Store (MDS) user interface](doc:metadata-store-mds-user-documentation). provides an alternative for registering DataCite DOIs. 

## Authentication

All requests to the MDS API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Metadata Store (MDS) uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

To start interacting with our DataCite Metadata Store (MDS) API you must request an account:
* If you are a DataCite Member, DataCite will provide you a username and password
* If you are a DataCite User, your Allocating Member will provide you a username and password
*  If you are not yet a DataCite Member or User, you can [obtain test credentials to our sandbox](doc:obtain-test-account)

Remember our accounts have basic security constraints:

* you will be allowed to register DOI names only under the prefixes that have been assigned to you
* your DOI names can only refer to URLs under host domains you control
* depending on your Allocating Member, you may or may not have an unlimited number of DOIs available. You can negotiate your quota with your Allocating Member

## How to Use

The DataCite Metadata Store (MDS) API can be used directly by making HTTP requests with packages such as [cURL](https://curl.haxx.se/docs/manpage.html). Besides using the API directly there are a number of wrappers for the API that you can install to create DataCite DOIs, such as [Cirneco](https://github.com/datacite/cirneco). Please review the documentation of the respective package for installation instructions.


## Getting Started

In this tutorial we will look at two basic operations of the DataCite Metadata Store (MDS) userbase: creating Metadata records and creating DOI names. It must be stressed that both operations are necessary to mint DOIs.

Most applications will use an existing wrapper library in the language of your choice, but it's important to familiarise yourself with the underlying API HTTP methods first.

There's no easier way to kick the tires than through cURL.

Let's start by testing our setup. Open up a command prompt and enter the following command:

```shell
$ curl --user username:password https://mds.datacite.org/doi/10.5438/0012
https://schema.datacite.org/meta/kernel-4.0/index.html%
```

The response will the URL defined by the DOI use requested for.

Next, let's get the metadata associated with such DOI:

```shell
# GET /metadata/doi
$ curl --user username:password https://mds.datacite.org/metadata/10.5438/0012
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<resource xmlns="http://datacite.org/schema/kernel-4" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://datacite.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4/metadata.xsd">
    <identifier identifierType="DOI">10.5438/0012</identifier>
    <creators>
        <creator>
            <creatorName>DataCite Metadata Working Group</creatorName>
        </creator>
    </creators>
    <titles>
        <title>DataCite Metadata Schema Documentation for the Publication and Citation of Research Data v4.0</title>
    </titles>
    <publisher>DataCite e.V.</publisher>
    <publicationYear>2016</publicationYear>
    <contributors>
        <contributor contributorType="ProjectLeader">
            <contributorName>Starr, Joan</contributorName>
            <givenName>Joan</givenName>
            <familyName>Starr</familyName>
            <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org">0000-0002-7285-027X</nameIdentifier>
            <affiliation>California Digital Library</affiliation>
        </contributor>
        <contributor contributorType="ProjectLeader">
            <contributorName>Smaele, Madeleine de</contributorName>
            <givenName>Madeleine de</givenName>
            <familyName>Smaele</familyName>
            <affiliation>TU Delft</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Ashton, Jan</contributorName>
            <givenName>Jan</givenName>
            <familyName>Ashton</familyName>
            <affiliation>British Library</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Barton, Amy</contributorName>
            <givenName>Amy</givenName>
            <familyName>Barton</familyName>
            <affiliation>Purdue University Library</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Bradford, Tina</contributorName>
            <givenName>Tina</givenName>
            <familyName>Bradford</familyName>
            <affiliation>NRC/CISTI</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Ciolek‐Figiel, Anne</contributorName>
            <givenName>Anne</givenName>
            <familyName>Ciolek-Figiel</familyName>
            <affiliation>Inist‐CNRS</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Dietiker, Stefanie</contributorName>
            <givenName>Stefanie</givenName>
            <familyName>Dietiker</familyName>
            <affiliation>ETH Zürich</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Elliott, Jannean</contributorName>
            <givenName>Jannean</givenName>
            <familyName>Elliot</familyName>
            <affiliation>DOE/OSTI</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Genat, Berrit</contributorName>
            <givenName>Berrit</givenName>
            <familyName>Genat</familyName>
            <affiliation>TIB</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Harzenetter, Karoline</contributorName>
            <givenName>Karoline</givenName>
            <familyName>Harzenetter</familyName>
            <affiliation>GESIS</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Hirschmann, Barbara</contributorName>
            <givenName>Barbara</givenName>
            <familyName>Hirschmann</familyName>
            <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org">0000-0003-0289-0345</nameIdentifier>
            <affiliation>ETH Zürich</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Jakobsson, Stefan</contributorName>
            <givenName>Stefan</givenName>
            <familyName>Jakobsson</familyName>
            <affiliation>SND</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Mailloux, Jean‐Yves</contributorName>
            <givenName>Jean-Yves</givenName>
            <familyName>Mailloux</familyName>
            <affiliation>NRC/CISTI</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Newbold, Elizabeth</contributorName>
            <givenName>Elizabeth</givenName>
            <familyName>Newbold</familyName>
            <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org">0000-0002-8255-9013</nameIdentifier>
            <affiliation>British Library</affiliation>
        </contributor>
                <contributor contributorType="Editor">
            <contributorName>Nielsen, Lars Holm </contributorName>
            <givenName>Lars Holm</givenName>
            <familyName>Nielsen</familyName>
            <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org">0000-0001-8135-3489</nameIdentifier>
            <affiliation>CERN</affiliation>
        </contributor>
        <contributor contributorType="Editor">
            <contributorName>Yahia, Mohamed</contributorName>
            <givenName>Mohamed</givenName>
            <familyName>Yahia</familyName>
            <affiliation>Inist-CNRS</affiliation>
        </contributor>
        <contributor contributorType="Supervisor">
            <contributorName>Ziedorn, Frauke</contributorName>
            <givenName>Frauke</givenName>
            <familyName>Ziedorn</familyName>
            <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org">0000-0002-1143-781X</nameIdentifier>
            <affiliation>TIB</affiliation>
        </contributor>
    </contributors>
    <language>eng</language>
    <resourceType resourceTypeGeneral="Text">Documentation</resourceType>
    <relatedIdentifiers>
        <relatedIdentifier relatedIdentifierType="DOI" relationType="Documents">10.5438/0013</relatedIdentifier>
        <relatedIdentifier relatedIdentifierType="DOI" relationType="IsNewVersionOf">10.5438/0010</relatedIdentifier>
    </relatedIdentifiers>
    <sizes>
        <size>45 pages</size>
    </sizes>
    <formats>
        <format>application/pdf</format>
    </formats>
    <version>4.0</version>
    <descriptions>
        <description descriptionType="TableOfContents">1 Introduction<br/>
1.1 The DataCite Consortium<br/>
1.2 DataCite Community Participation<br/>
1.3 The Metadata Schema<br/>
1.4 Version 4.0 Update<br/>
2 DataCite Metadata Properties<br/>
2.1 Overview<br/>
2.2 Citation<br/>
2.3 DataCite Properties<br/>
3 XML Example<br/>
4 XML Schema<br/>
5 Other DataCite Services<br/>
Appendices<br/>
Appendix 1: Controlled List Definitions<br/>
Appendix 2: Earlier Version Update Notes</description>
    </descriptions>
</resource>
```
Mmmmm, tastes like XML. Let's add the `-i` flag to include headers:

```shell
# GET /metadata/doi
$ curl --user username:password https://mds.datacite.org/metadata/10.5438/0012 -i
```

```json
HTTP/1.1 200 OK
Server: openresty/1.11.2.1
Date: Wed, 04 Jan 2017 11:44:46 GMT
Content-Type: application/xml;charset=UTF-8
Content-Length: 6258
Connection: keep-alive
Pragma: no-cache
Expires: Thu, 01 Jan 1970 00:00:00 GMT
Cache-Control: no-cache
Cache-Control: no-store
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, POST, OPTIONS

<?xml version="1.0" encoding="UTF-8"?>
<resource xmlns="http://datacite.org/schema/kernel-4" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
```

There are a few interesting bits in the response headers. As expected, the Content-Type is `application/xml`. Additional responses status include: `200 OK`: operation successful; `204 No Content` : DOI is known to DataCite Metadata Store (MDS), but is not minted (or not resolvable e.g. due to handle's latency); `401 Unauthorized`: no login; `403` : - login problem or dataset belongs to another party; `404 Not Found`: DOI does not exist in our database.

### Registering DOIs

Almost any meaningful use of the DataCite Metadata Store (MDS) API will involve some level of DOI registration. There are three steps to follow in order to perform this daunting operation. Here we will help you ease this task. First, we need to generate a DOI name. Then, we need to create a metadata record (and this is the correct order to do so). Finally, we register the DOI.

#### Generating a DOI name


You will need to generate a name for your DOI. The only condition is that the name is unique. DataCite recommends that only the following characters are used within a DOI name: `0-9`, `a-z`, `A-Z`, `- (dash)`, `. (dot)`, `_ (underscore)`, `+ (plus)`, `: (colon)` and `/ (slash)`. An example of a DOI name would be `10.5438/0012`.

However, a better way to generate names is using the [Cirneco](https://github.com/datacite/cirneco) wrapper. From your terminal, one just needs to write a one-liner to generate DOI Names. Reminder: when generating DOI names using Cirneco you are not in anyway linking these names to the DataCite Metadata storage. This operation only helps to create well formatted DOI Names. Therefore you can generate as many DOI Names as you wish.

```shell
$ cirneco doi generate --prefix=10.5072
10.5072/JQX3-61AT
```

We strongly recommend using the `cirneco` wrapper to perform this operation, as there are a number of advantages when creating DOI names this way. For more information please visit the [Cirneco documentation](https://github.com/datacite/cirneco).

#### Adding a Metadata Record

To add metadata to a DOI, we need to `POST`  XML containing the details of the DOI record. Metadata about your datasets must conform to the standards published by DataCite in the [Metadata Schema](http://schema.datacite.org). There you will find the preferred version and example XML document. Please remember that all your documents must specify the correct schema location in the root element. Also, make sure the DOI specified in your document matches the DOI of the dataset. For example, here we saved the metadata in a `xml` file named `10.5072/JQX3-61AT.xml`. Finally, do not forget to include the content type for the metadata as this is mandatory.

```shell
# POST /metadata
$ curl -H "Content-Type:application/xml;charset=UTF-8" -X POST -i --user username:password -d @10.5072/JQX3-61AT.xml https://mds.test.datacite.org/metadata
```

The response to this call will return a short explanation of status code e.g. CREATED, HANDLE_ALREADY_EXISTS etc. Other responses status include: `201 Created`: operation successful, `400 Bad Request`: invalid XML, wrong prefix, `401 Unauthorised`: no login, `403 Forbidden`: login problem, quota exceeded, '415 Wrong Content Type': Not includding content type in the header.


In Python you can create a metadata record as follows:

```python
import requests, sys, codecs
  #endpoint = 'https://mds.datacite.org/metadata'
  endpoint = 'https://mds.test.datacite.org/metadata'
  if (len(sys.argv) < 4):
    raise Exception('Please provide username, password and location of metadata file')
    username, password, filename = sys.argv[1:]
    metadata = codecs.open(filename, 'r', encoding='utf-8').read()
    response = requests.post(endpoint,
      auth = (username, password),
      data = metadata.encode('utf-8'),
      headers = {'Content-Type':'application/xml;charset=UTF-8'})
    print str(response.status_code) + " " + response.text
```

We can perform the same operation using the `cirneco` wrapper. First, create XML metadata file in the directory from which you will run the `cirneco` command.

```shell
$ cirneco metadata post 10.5072/JQX3-61AT.xml
```

Once you have created the record, you can fetch the metadata record using either approach.

In Python:

```python
import requests, sys, codecs
  #endpoint = 'https://mds.datacite.org/metadata'
  endpoint = 'https://mds.test.datacite.org/metadata'
  if (len(sys.argv) < 4):
    raise Exception('Please provide username, password and location of metadata file')
    username, password, filename = sys.argv[1:]
    metadata = codecs.open(filename, 'r', encoding='utf-8').read()
    response = requests.post(endpoint,
      auth = (username, password),
      data = metadata.encode('utf-8'),
      headers = {'Content-Type':'application/xml;charset=UTF-8'})
    print str(response.status_code) + " " + response.text
```

or alternatively using the `cirneco` wrapper:

```shell
$ cirneco metadata get 10.5072/JQX3-61AT
Metadata for 10.5072/JQX3-61AT saved as JQX3-61AT.xml
```

This last example will save the metadata in a XML file 10.5072/JQX3-61AT.xml.

#### Registering a DOI

The next step is to register the DOI name. We can `POST` DOIs in a similar way to how we fetched DOI details earlier. A file with the DOI name for the new resource and the URL where the resource is located needs to be provided.

```text
#Content-Type:text/plain;charset=UTF-8
doi= 10.5072/JQX3-61AT
url= http://example.org/
```

```shell
# PUT /doi
$ curl -H "Content-Type:text/plain;charset=UTF-8" -X PUT --user username:password -d doi=10.5072/JQX3-61AT\nurl=http://example.org/ https://mds.test.datacite.org/doi/10.5072/JQX3-61AT
```

This method will mint new a DOI if the specified DOI doesn't exist. However, this method will attempt to update the URL if you specify an existing DOI. Standard domains and quota restrictions check will be performed. A datacentre's DOI `QuotaUsed` will be increased by 1. A new record in Datasets will be created.

The response is a short explanation of status code (e.g. CREATED, HANDLE_ALREADY_EXISTS etc). Additional reponses include: `201 Created`: operation successful; `400 Bad Request`: request body must be exactly two lines: DOI and URL; wrong domain, wrong prefix;
`401 Unauthorised`: no login; `403 Forbidden`: login problem, quota exceeded; `412 Precondition failed`: metadata must be uploaded first.

The same `POST` request could be implemented in Python as follows:

```python
import requests, sys, codecs
  #endpoint = 'https://mds.datacite.org/doi'
  endpoint = 'https://mds.test.datacite.org/doi'
  if (len(sys.argv) < 4):
    raise Exception('Please provide username, password, location of doi-url file')
    username, password, filename = sys.argv[1:]
    file = codecs.open(sys.argv[3], 'r', encoding='utf-8').read().strip()
    response = requests.put(endpoint,
      auth = (username, password),
      data = file.encode('utf-8'),
      headers = {'Content-Type':'text/plain;charset=UTF-8'})
    print str(response.status_code) + " " + response.text
```

or from the command line using the CLI wrapper `cirneco`. The following `cirneco` command for registering DOIs uses a markdown file with metadata in YAML front matter, that should be placed in the same directory or as option parameters.

```json
----
doi: 10.5072/JQX3-61AT
url: http://example.org/
----
```

```shell
$ cirneco doi put 10.5072/JQX3-61AT --url http://example.org/
```

In the same way, we can fetch the DOI we just registered. However, there is a caveat. It is important to understand that the [Handle System](http://handle.net) (the technical infrastructure for DOI resolution) is a distributed network system. The consequence of this manifests is its inherent **latency**. For example, DOIs have TTL (time to live) defaulted to **24 hours**, so your changes will be visible to the resolution infrastructure only when the TTL expires. Also, if you create a DOI and then immediately try to update its URL, you might get the error message HANDLE NOT EXISTS (`404` or `204`). **This is because it takes some time for the system to register a handle for a DOI**.

```shell
$ curl -X GET --user username:password https://mds.datacite.org/doi/10.5072/JQX3-61AT
https://doi.org/10.5072/JQX3-61AT
```

in Python that would be:

```python
import requests, sys
  #endpoint = 'https://mds.datacite.org/doi'
  endpoint = 'https://mds.test.datacite.org/doi'
  if (len(sys.argv) < 4):
    raise Exception('Please provide username, password and doi')
    username, password, doi = sys.argv[1:]
    response = requests.get(endpoint + '/' + doi,
      auth = (username, password))
  if (response.status_code != 200):
    print str(response.status_code) + " " + response.text
  else:
    print response.text
```

and using the `cirneco` wrapper it would be as follows:

```shell
$ cirneco doi get 10.5072/JQX3-61AT
http://example.org/
```

Woot! Now you know the basics of the DataCite Metadata Store (MDS) API! You learned:

- Basic authentication
- Fetching and registering DOI names and Metadata records.

Keep learning with the [API Live Reference](https://datacite.readme.io/v1.0/reference#overview) where you can make requests directly.



[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]