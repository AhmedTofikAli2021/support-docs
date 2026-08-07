---
title: EZ API
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
The DataCite EZ API allows registration of DOIs and DOI metadata, and tries to be as compatible as possible with the [EZID API](https://ezid.cdlib.org/doc/apidoc.html) from the California Digital Library. The service launched in March 2018. While we try to implement features added to the EZID service going forward, no guarantees are made doing so. Because of some fundamental differences between the services provided by EZID and DataCite, some functionalities make no sense as a DataCite service and have not been implemented, including

* Registration of identifiers other than DataCite DOIs, including ARKs
* Crossref registration

Some features have not yet been implemented as of March 2018, but are planned for Q1 and Q2 2018 (see [DataCite roadmap](https://www.datacite.org/roadmap.html) for details):

* Registration of metadata in other formats, e.g. Dublin Core
* Tombstone page for all registered DOIs

Requests for the functionality of the EZID service not (yet) implemented will return appropriate error codes, e.g. a status `501 not implemented`.

Some features of the DataCite service are not available in the EZID service, for example the following metadata profiles:

* bibtex
* ris
* schema.org (use profile `schema_org`)
* Citeproc JSON (using profile `citeproc`)

The `crossref` metadata profile will register a DataCite DOI using metadata in Crossref Unixref format instead of registering the DOI with Crossref.

The base URL of the service is `https://ez.datacite.org`.

### API vs. UI

The EZID-compatible API provided by DataCite is complemented by the user interface of the DOI Fabrica service available at [https://doi.datacite.org](https://doi.datacite.org). The UI can be used to manage registered DOIs, and to reset the password.

### Authentication

Most requests require authentication. The API supports HTTP Basic authentication, using the same username and password as for the Metadata Store (MDS) and DOI Fabrica service. With this method, the client supplies HTTP Basic authentication credentials on every request. 

In contrast to the [EZID API](https://ezid.cdlib.org/doc/apidoc.html#authentication), the DataCite EZ API does not support one-time login via the `/login` path, with login credentials then stored in a session cookie. Instead, an error message will be returned.

For example, credentials for HTTP basic authentication can be added manually in Python as follows:

```
import base64, urllib2
r = urllib2.Request("https://ez.datacite.org/...")
r.add_header("Authorization", "Basic " + base64.b64encode("username:password"))
```

But most programming libraries provide higher-level support for authentication. For example, Python provides HTTPBasicAuthHandler:

```
import urllib2
h = urllib2.HTTPBasicAuthHandler()
h.add_password("ez.datacite.org", "https://ez.datacite.org", "username", "password")
o = urllib2.build_opener(h)
o.open("https://ez.datacite.org/...")
```

The downside of using higher-level authentication mechanisms is that they often do not supply credentials initially, but only in response to a challenge from the service, thus doubling the number of HTTP transactions.

To manually provide credentials in Java, using Apache Commons Codec to do the Base64 encoding:

```
import java.net.*;
import org.apache.commons.codec.binary.*;

URL u = new URL("https://ez.datacite.org.org/...);
URLConnection c = u.openConnection();
c.setRequestProperty("Accept", "text/plain");
c.setRequestProperty("Authorization", "Basic " +
  new String(Base64.encodeBase64("username:password".getBytes())));
c.connect();
```

Java also provides an Authenticator class:

```
import java.net.*;

class MyAuthenticator extends Authenticator {
  protected PasswordAuthentication getPasswordAuthentication () {
    return new PasswordAuthentication("username", "password".toCharArray());
  }
}

Authenticator.setDefault(new MyAuthenticator());
```

If authentication is required and credentials are either missing or invalid, the service returns a 401 HTTP status code and the status line "error: unauthorized" (see [Error handling](#error-handling) below). If authentication is successful but the request is still not authorized, the service returns a 403 HTTP status code and the status line "error: forbidden".

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

### Ownership model

The service maintains ownership information about identifiers and uses that information to enforce access control.

The ownership model employed by DataCite is based on clients: each identifier is owned by one client. Permission to create identifiers is governed by the prefixes that have been assigned to a client by it's DOI Service Provider. But once created, permission to subsequently modify an identifier is governed solely by the identifier's ownership.

Clients in turn are managed by DOI service providers, including the assignment of prefixes and users to clients.

### Identifier status

Each identifier in the service has a status. The status is recorded as the value of the "_status" reserved metadata element (see Internal metadata below) and may be one of:

* **public**. The default value.
* **reserved**. The identifier is known only to DataCite. This status may be used to reserve an identifier name within DataCite without advertising the identifier's existence to resolvers and other external services. A reserved identifier may be deleted.
* **unavailable**. The identifier is public, but the object referenced by the identifier is not available. A reason for the object's unavailability may optionally follow the status separated by a pipe character ("|", U+007C), e.g., "unavailable | withdrawn by author". The identifier redirects to a "tombstone" page (an HTML page that displays the identifier's citation metadata and the reason for the object's unavailability) regardless of its target URL.

An identifier's status may be changed by setting a new value for the aforementioned "_status" metadata element. DataCite permits only certain status transitions:

* A status of "reserved" may be specified only at identifier creation time.
* A reserved identifier may be made public. At this time the identifier will be registered with resolvers and other external services.
* A public identifier may be marked as unavailable. At this time the identifier will be removed from any external services.
* An unavailable identifier may be returned to public status. At this time the identifier will be re-registered with resolvers and other external services.