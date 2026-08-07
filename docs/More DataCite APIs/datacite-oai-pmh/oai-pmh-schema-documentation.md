---
title: OAI-PMH Schema Documentation
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
This schema has been created specifically for the dissemination of DataCite metadata using OAI-PMH. It contains the following elements under the http://schema.datacite.org/oai/oai-1.1/ XML namespace:

datacentreSymbol - the symbol of the data centre that registered this dataset.
schemaVersion - the estimated DataCite Metadata Schema version that this record adheres to.
payload - the complete metadata of this record.

See the full [DataCite Metadata Schema](http://schema.datacite.org/) for descriptions of the different elements.
[block:code]
{
  "codes": [
    {
      "code": "  <oai_datacite xmlns=\"http://schema.datacite.org/oai/oai-1.1/\" xsi:schemaLocation=\"http://schema.datacite.org/oai/oai-1.1/ http://schema.datacite.org/oai/oai-1.1/oai.xsd\">\n          <schemaVersion>3</schemaVersion>\n          <datacentreSymbol>BL.ADS</datacentreSymbol>\n          <payload>\n            <resource xmlns=\"http://datacite.org/schema/kernel-3\" xsi:schemaLocation=\"http://datacite.org/schema/kernel-3 http://schema.datacite.org/meta/kernel-3/metadata.xsd\">\n  <identifier identifierType=\"DOI\">10.5284/1000389</identifier>\n  <creators>\n    <creator>\n      <creatorName>H E M Cool</creatorName>\n    </creator>\n    <creator>\n      <creatorName>Mark Bell</creatorName>\n    </creator>\n  </creators>\n  <titles>\n    <title>Excavations at St Peter's Church, Barton-upon-Humber</title>\n  </titles>\n  <publisher>Archaeology Data Service</publisher>\n  <publicationYear>2011</publicationYear>\n  <subjects>\n    <subject subjectScheme=\"LCSH\">Archaeology</subject>\n    <subject subjectScheme=\"FISH Archaeological Objects (England)\">BEAD</subject>\n    <subject subjectScheme=\"FISH Archaeological Objects (England)\">CERAMIC</subject>\n    <subject subjectScheme=\"Monument Type (England)\">CHURCH</subject>\n    <subject subjectScheme=\"FISH Archaeological Objects (England)\">COIN</subject>\n    <subject subjectScheme=\"Monument Type (England)\">ENCLOSURE</subject>\n    <subject subjectScheme=\"FISH Archaeological Objects (England)\">FLOOR TILE</subject>\n    <subject subjectScheme=\"FISH Archaeological Objects (England)\">Human Bone</subject>\n    <subject subjectScheme=\"Monument Type (England)\">INHUMATION CEMETERY</subject>\n    <subject subjectScheme=\"FISH Archaeological Objects (England)\">PIN</subject>\n  </subjects>\n  <contributors>\n    <contributor contributorType=\"Funder\">\n      <contributorName>English Heritage</contributorName>\n    </contributor>\n    <contributor contributorType=\"RightsHolder\">\n      <contributorName>Barbican Research Associates</contributorName>\n    </contributor>\n  </contributors>\n  <dates>\n    <date dateType=\"Created\">1974/2010</date>\n  </dates>\n  <language>en</language>\n  <resourceType resourceTypeGeneral=\"Dataset\">Archive</resourceType>\n  <alternateIdentifiers>\n    <alternateIdentifier alternateIdentifierType=\"ADS Collection ID\">1030</alternateIdentifier>\n  </alternateIdentifiers>\n  <formats>\n    <format>application/pdf</format>\n    <format>text/csv</format>\n  </formats>\n  <version>1</version>\n  <rightsList>\n    <rights rightsURI=\"http://archaeologydataservice.ac.uk/advice/termsOfUseAndAccess\">ADS Terms and Conditions apply to reuse</rights>\n  </rightsList>\n  <descriptions>\n    <description descriptionType=\"Other\">St Peter's Church at Barton-upon-Humber (TA 0347 2194) was declared redundant in 1972 and taken into public guardianship in 1978 by the then Department of Environment. Given that it had long been recognised that it had a late Saxon origin, a major programme of excavation and survey was instituted. This explored the church and its churchyard, and ran from 1978 to 1984 under the direction of Warwick Rodwell. The programme has meant that this is the most intensively studied and recorded parish church in the country. It also produced the largest collection of human remains ever excavated in the UK. The latter provide a unique insight into the population of a small, relatively isolated, market town over 900 years.</description>\n  </descriptions>\n  <geoLocations>\n    <geoLocation>\n      <geoLocationPoint>52.785123 -0.467239</geoLocationPoint>\n      <geoLocationPlace>England</geoLocationPlace>\n    </geoLocation>\n  </geoLocations>\n</resource>\n          </payload>\n        </oai_datacite>\n      </metadata>\n    </record>\n  </GetRecord>\n</OAI-PMH>",
      "language": "xml"
    }
  ]
}
[/block]