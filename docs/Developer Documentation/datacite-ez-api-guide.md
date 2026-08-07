---
title: DataCite EZ API Guide
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
## Purpose of the DataCite EZ API

The base URL of the service is `https://ez.datacite.org`.

The [DataCite EZ API](https://support.datacite.org/v1.1/reference#ez-api) was designed to assist those of our clients who transitioned from the California Digital Library (CDL) EZID service. The API is compatible with the [EZID API](https://ezid.cdlib.org/doc/apidoc.html) from the California Digital Library and is intended for previous users of that API. 

Note that the EZ API was not intended to be a permanent solution. New DataCite services and functionalities are not added to the EZ API. Users wanting the latest features should instead use the [DataCite REST API](doc:api) . 

## Limitations of the DataCite EZ API

Because of fundamental differences between the services provided by EZID and DataCite, some functionalities available from EZID have not been implmented in the DataCite EZ API. These include: 

* Registration of identifiers other than DataCite DOIs, including ARKs
* Crossref registration
* Registration of metadata in other formats, e.g. Dublin Core
* Tombstone page for all registered DOIs

Requests for the above functionalities will return appropriate error codes, e.g. a status `501 not implemented`.

Similarly, the following DataCite metadata profiles are not available via the DataCite EZ API:

* bibtex
* ris
* schema.org (use profile 'schema_org')
* Citeproc JSON (using profile 'citeproc')

The `crossref` metadata profile will register a DataCite DOI using metadata in Crossref Unixref format instead of registering the DOI with Crossref.

## Authentication

Your username and password for the EZ API are the same as your username and password for the MDS API, DOI Fabrica, and the REST API. 

All requests to the EZ API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite EZ API uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

In contrast to the [EZID API](https://ezid.cdlib.org/doc/apidoc.html#authentication), the DataCite EZ API does not support one-time login via the `/login` path, with login credentials then stored in a session cookie. Instead, an error message will be returned.

If authentication is required and credentials are either missing or invalid, the service returns a 401 HTTP status code and the status line "error: unauthorized" (see [Error handling](#error-handling) below). If authentication is successful but the request is still not authorized, the service returns a 403 HTTP status code and the status line "error: forbidden".

## How to use the EZ API

The DataCite EZ API can be used directly by making HTTP requests with packages such as [cURL](https://curl.haxx.se/docs/manpage.html). Besides using the API directly there are a number of wrappers for the API that you can install to create DataCite DOIs. Please review the documentation of the respective package for installation instructions, and make sure you point your client to https://ez.datacite.org instead of https://ezid.cdlib.org.

* **EZID** (Python) - https://ezid.cdlib.org/doc/apidoc.html#python-command-line-tool
* **EZID Client** (Ruby) - https://github.com/duke-libraries/ezid-client
* **EZID-PHP** (PHP) - https://github.com/olendorf/ezid-php

### Example cURL request

Using cURL it is easiest to create a data file e.g. "payload.txt" and in that put your ANVL formatted request (see above).
You can then make a call like
```curl --user xxx:xxx -X POST -H 'Content-Type: text/plain' --data-binary @payload.txt https://ez.test.datacite.org/shoulder/doi:10.5438```

### Request & response bodies

Request and response bodies are used to transmit identifier metadata. The HTTP content type for all bodies is "text/plain" using UTF-8 charset encoding. In request bodies, if no charset encoding is declared in the HTTP Content-Type header, it is assumed to be UTF-8.

The service's data model for metadata is a dictionary of element name/value pairs. The dictionary is single-valued: an element name may not be repeated. Names and values are strings. Leading and trailing whitespace in names and values is not significant. Neither element names nor element values may be empty. (When modifying an identifier, an uploaded empty value is treated as a command to delete the element entirely.)

Metadata dictionaries are serialized using a subset of [A Name-Value Language (ANVL)](https://confluence.ucop.edu/display/Curation/Anvl) rules:

* One element name/value pair per line.
* Names separated from values by colons.

For example:

```
who: Proust, Marcel
what: Remembrance of Things Past
when: 1922
```

In addition, two ANVL features may be used when uploading metadata to the service (but clients can safely assume that DataCite will never use these features when returning metadata):

* A line beginning with a number sign ("#", U+0023) is a comment and will be ignored.
* A line beginning with whitespace continues the previous line (the intervening line terminator and whitespace are converted to a single space).

For example:

```
# The following two elements are identical:
who: Proust,
  Marcel
who: Proust, Marcel
```

Care must be taken to escape structural characters that appear in element names and values, specifically, line terminators (both newlines ("\n", U+000A) and carriage returns ("\r", U+000D)) and, in element names, colons (":", U+003A). EZID employs percent-encoding as the escaping mechanism, and thus percent signs ("%", U+0025) must be escaped as well. In Python, a dictionary of Unicode metadata element names and values, metadata, is serialized into a UTF-8 encoded string, anvl, with the following code:

```
import re

def escape (s):
  return re.sub("[%:\r\n]", lambda c: "%%%02X" % ord(c.group(0)), s)

anvl = "\n".join("%s: %s" % (escape(name), escape(value)) for name,
  value in metadata.items()).encode("UTF-8")
```

Conversely, to parse a UTF-8 encoded string, anvl, producing a dictionary, metadata:

```
import re

def unescape (s):
  return re.sub("%([0-9A-Fa-f][0-9A-Fa-f])",
    lambda m: chr(int(m.group(1), 16)), s)

metadata = dict(tuple(unescape(v).strip() for v in l.split(":", 1)) \
  for l in anvl.decode("UTF-8").splitlines())
```

In Java, to serialize a HashMap of metadata element names and values, metadata, into an ANVL-formatted Unicode string, anvl:

```
import java.util.*;

String escape (String s) {
  return s.replace("%", "%25").replace("\n", "%0A").
    replace("\r", "%0D").replace(":", "%3A");
}

Iterator<Map.Entry<String, String>> i = metadata.entrySet().iterator();
StringBuffer b = new StringBuffer();
while (i.hasNext()) {
  Map.Entry<String, String> e = i.next();
  b.append(escape(e.getKey()) + ": " + escape(e.getValue()) + "\n");
}
String anvl = b.toString();
```

And conversely, to parse a Unicode ANVL-formatted string, anvl, producing a HashMap, metadata:

```
import java.util.*;

String unescape (String s) {
  StringBuffer b = new StringBuffer();
  int i;
  while ((i = s.indexOf("%")) >= 0) {
    b.append(s.substring(0, i));
    b.append((char) Integer.parseInt(s.substring(i+1, i+3), 16));
    s = s.substring(i+3);
  }
  b.append(s);
  return b.toString();
}

HashMap<String, String> metadata = new HashMap<String, String>();
for (String l : anvl.split("[\\r\\n]+")) {
  String[] kv = l.split(":", 2);
  metadata.put(unescape(kv[0]).trim(), unescape(kv[1]).trim());
}
```

The first line of an EZID response body is a status indicator consisting of "success" or "error", followed by a colon, followed by additional information. Two examples:

```
success: ark:/99999/fk4test
error: bad request - no such identifier
```

### Error handling

An error is indicated by both an HTTP status code and an error status line of the form "error: reason". For example:

```
⇒ GET /id/doi:/10.5072/bogus HTTP/1.1
⇒ Host: ez.datacite.org

⇐ HTTP/1.1 400 BAD REQUEST
⇐ Content-Type: text/plain; charset=UTF-8
⇐ Content-Length: 39
⇐
⇐ error: bad request - no such identifier
```

Some programming libraries make it a little difficult to read the content following an error status code. For example, from Java, it is necessary to explicitly switch between the input and error streams based on the status code:

```
java.net.HttpURLConnection c;
java.io.InputStream s;
...
if (c.getResponseCode() < 400) {
  s = c.getInputStream();
} else {
  s = c.getErrorStream();
}
// read from s...
```

## DataCite MetaData Profile
The EZ API supports the deposition of metadata in DataCite XML format following the [DataCite metadata schema](http://schema.datacite.org/). This must be passed to the API via the ANVL format, i.e. with proper escaping of new lines and colons (which have special meaning in ANVL). For example:

```xml

_target: https%3A//example.org/abc
<?xml version="1.0" encoding="UTF-8"?>%0A<resource xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://datacite.org/schema/kernel-4" xsi:schemaLocation="http://datacite.org/schema/kernel-4 %0A " target="_blank" rel="noopener noreferrer">http://schema.datacite.org/meta/kernel-4/metadata.xsd">%0A  <identifier identifierType="DOI">10.33516/F8X6-9F20</identifier>%0A  <creators>%0A    <creator>%0A      <creatorName>Test User</creatorName>%0A    </creator>%0A  </creators>%0A  <titles>%0A    <title>Aqueous geochemistry of Louisiana marshes, May 2015 – October 2016</title>%0A  </titles>%0A  <publisher>Harte Research Institute</publisher>%0A  <publicationYear>2018</publicationYear>%0A  <resourceType resourceTypeGeneral="Dataset">CreativeWork</resourceType>%0A  <dates>%0A    <date dateType="Issued">2018</date>%0A  </dates>%0A  <version/>%0A</resource>%0A

```

### Resource types
When specifying the DataCite metadata profile it is important you send the correct resource type for the DOI you are registering, in some cases third party libraries may put defaults that are invalid e.g. "Book"

### DOI states

Each DataCite DOI has a state. The terminology used in the DataCite EZ API mimics the terminology used in the original EZID service.

* **public**. The default value.
* **reserved**. The identifier is known only to DataCite. This status may be used to reserve an identifier name within DataCite without advertising the identifier's existence to resolvers and other external services. A reserved identifier may be deleted.
* **unavailable**. The identifier is public, but the object referenced by the identifier is not available. A reason for the object's unavailability may optionally follow the status separated by a pipe character ("|", U+007C), e.g., "unavailable | withdrawn by author". Note that unlike EZID, DataCite does not automatically provide tombstone pages for DOIs marked as unavailable. The client will need to update the URL in the DOI metadata to point to a valid tombstone page.  

A DOI's state may be changed by setting a new value for the "_status" reserved metadata element. 

See [DOI States](doc:doi-states) for further information on states and the allowed transitions between them. 

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]