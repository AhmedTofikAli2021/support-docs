---
title: Consuming Views and Downloads
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
Usage counts (views and downloads) are shared through DataCite's APIs and visible in [DataCite Commons](doc:datacite-commons).

## DataCite Event Data

Usage counts can be consumed directly from DataCite through DataCite Event Data. 

To retrieve usage counts for a specific DOI, we need to call the `events` endpoint and filter by`source-id`: `datacite-usage` and`doi`. 

Example request: <https://api.datacite.org/events?source-id=datacite-usage&doi=10.7272/q6rx997g>

Example response:

```json
{
"data": [
{
"id": "20e6ea05-8650-4b59-b1b0-7ece6bb0d31b",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-regular",
"total": 98,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-05-01T00:00:00.000Z",
"timestamp": "2019-11-02T00:24:23.374Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "c74a42c8-0b27-42b7-91d8-b1a3b541c904",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-requests-regular",
"total": 1,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-05-01T00:00:00.000Z",
"timestamp": "2019-11-02T00:24:23.445Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "c7364380-27a2-45ac-97fb-01fb96654115",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-requests-regular",
"total": 1,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-05-01T00:00:00.000Z",
"timestamp": "2019-11-02T00:25:10.058Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "eb4caa48-63ec-4087-b6ec-33efbc01d9a8",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-investigations-regular",
"total": 14,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-05-01T00:00:00.000Z",
"timestamp": "2019-11-02T00:25:10.848Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/08761bb6-f8d9-4d01-8012-fd21042fd71d",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "a04c593d-bfd4-4625-a982-a604eea6c9d5",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-requests-regular",
"total": 5,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-11-01T00:00:00.000Z",
"timestamp": "2020-01-14T03:45:57.915Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "3a365169-3729-4d5d-b1c7-6134454dd992",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-investigations-regular",
"total": 36,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-11-01T00:00:00.000Z",
"timestamp": "2020-01-14T03:46:45.724Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "2ff5748a-19b0-4303-89c2-a2002961ec9f",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-regular",
"total": 42,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-11-01T00:00:00.000Z",
"timestamp": "2020-01-14T03:47:17.274Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "8f86a8da-bf52-46ea-8bec-7944b5b2719a",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-requests-regular",
"total": 5,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-11-01T00:00:00.000Z",
"timestamp": "2020-01-14T03:47:38.229Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/2a747c52-a2ef-4321-bca3-579d12e1f7d8",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "40fdc2c8-2f33-40a7-9b0c-7ebeb1d416dc",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-investigations-regular",
"total": 98,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-02-01T00:00:00.000Z",
"timestamp": "2020-03-06T15:15:28.961Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "c8161ecf-be09-438b-9d5f-f8318fc33cbe",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-machine",
"total": 1,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-02-01T00:00:00.000Z",
"timestamp": "2020-03-06T15:15:30.448Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "58891a9c-afd8-44e8-948f-e24fe42a3e81",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-regular",
"total": 113,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-02-01T00:00:00.000Z",
"timestamp": "2020-03-06T15:15:54.942Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "956133fe-2823-4793-9b50-af557f42fcd9",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-investigations-machine",
"total": 1,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-02-01T00:00:00.000Z",
"timestamp": "2020-03-06T15:15:56.411Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "cf165738-9643-4fc1-9084-d1afd3c60362",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-requests-regular",
"total": 3,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-02-01T00:00:00.000Z",
"timestamp": "2020-03-06T15:16:02.686Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "7adabc30-8e22-40f6-a594-56223e29473d",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-requests-regular",
"total": 5,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-02-01T00:00:00.000Z",
"timestamp": "2020-03-06T15:16:24.650Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/0c732186-e057-47d9-a5ee-a8121a26c4f9",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "740e2403-491c-4927-9b9c-d6909d50b462",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-requests-regular",
"total": 4,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-01-01T00:00:00.000Z",
"timestamp": "2020-03-06T16:20:14.415Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "5399c55f-f2c2-4c17-8a62-c519a8a9f4e0",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-requests-regular",
"total": 5,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-01-01T00:00:00.000Z",
"timestamp": "2020-03-06T16:31:18.051Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "7bdf4c02-3fd4-4e16-a275-1b9c27919dda",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-regular",
"total": 124,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-01-01T00:00:00.000Z",
"timestamp": "2020-03-06T16:31:41.969Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "c16f39b5-340f-42ba-a7b0-80a6d3a9b086",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-investigations-regular",
"total": 100,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-01-01T00:00:00.000Z",
"timestamp": "2020-03-06T16:35:59.546Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/d144bbc1-ca4e-434d-a32f-aadd2f386765",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "84b448d2-ef34-4f28-99a5-75ab9371a459",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-regular",
"total": 44,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-12-01T00:00:00.000Z",
"timestamp": "2020-03-07T01:19:54.339Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "e240afd1-6a94-41a9-b30f-616b61766baa",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-requests-regular",
"total": 15,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-12-01T00:00:00.000Z",
"timestamp": "2020-03-07T01:19:54.854Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "0e3c76f7-c67f-461c-abe8-360adf32c90e",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-requests-regular",
"total": 9,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-12-01T00:00:00.000Z",
"timestamp": "2020-03-07T01:20:27.141Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "267481eb-f4ac-47bd-9c61-fd9f628dfc4c",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "unique-dataset-investigations-regular",
"total": 35,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2018-12-01T00:00:00.000Z",
"timestamp": "2020-03-07T01:20:28.951Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/87346bcf-2b80-4768-a458-a0d92c77e66e",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "cc7a51a9-6f07-4104-bceb-4cb707626fc9",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/073f27b5-d38b-4301-ab73-3274ba3eb672",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-requests-regular",
"total": 7,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-05-01T00:00:00.000Z",
"timestamp": "2020-03-07T03:50:49.840Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/073f27b5-d38b-4301-ab73-3274ba3eb672",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "cd1563e5-8098-4ad9-81c4-7a13c7c02f44",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/073f27b5-d38b-4301-ab73-3274ba3eb672",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-machine",
"total": 1,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-05-01T00:00:00.000Z",
"timestamp": "2020-03-07T03:52:21.927Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/073f27b5-d38b-4301-ab73-3274ba3eb672",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
},
{
"id": "bb5de4a5-d4c0-41a2-acf7-a174a434b482",
"type": "events",
"attributes": {
"subj-id": "https://api.datacite.org/reports/073f27b5-d38b-4301-ab73-3274ba3eb672",
"obj-id": "https://doi.org/10.7272/q6rx997g",
"source-id": "datacite-usage",
"relation-type-id": "total-dataset-investigations-regular",
"total": 29,
"message-action": "create",
"source-token": "43ba99ae-5cf0-11e8-9c2d-fa7ae01bbebc",
"license": "https://creativecommons.org/publicdomain/zero/1.0/",
"occurred-at": "2019-05-01T00:00:00.000Z",
"timestamp": "2020-03-07T03:53:30.659Z"
},
"relationships": {
"subj": {
"data": {
"id": "https://api.datacite.org/reports/073f27b5-d38b-4301-ab73-3274ba3eb672",
"type": "objects"
}
},
"obj": {
"data": {
"id": "https://doi.org/10.7272/q6rx997g",
"type": "objects"
}
}
}
}
],
"meta": {
"total": 182,
"total-pages": 8,
"page": 1,
"sources": [
{
"id": "datacite-usage",
"title": "DataCite Usage Stats",
"count": 182
}
],
"occurred": [
{
"id": "2021",
"title": "2021",
"count": 40
},
{
"id": "2020",
"title": "2020",
"count": 46
},
{
"id": "2019",
"title": "2019",
"count": 56
},
{
"id": "2018",
"title": "2018",
"count": 40
}
],
"prefixes": [
{
"id": "10.7272",
"title": "10.7272",
"count": 182
}
],
"citation-types": [],
"relation-types": [
{
"id": "total-dataset-investigations-regular",
"title": "total-dataset-investigations-regular",
"count": 42,
"year-months": [
{
"id": "2021-09",
"title": "2021-09",
"sum": 1
},
{
"id": "2021-08",
"title": "2021-08",
"sum": 1
},
{
"id": "2021-07",
"title": "2021-07",
"sum": 1
},
{
"id": "2021-06",
"title": "2021-06",
"sum": 1
},
{
"id": "2021-05",
"title": "2021-05",
"sum": 1
},
{
"id": "2021-04",
"title": "2021-04",
"sum": 1
},
{
"id": "2021-03",
"title": "2021-03",
"sum": 1
},
{
"id": "2021-02",
"title": "2021-02",
"sum": 1
},
{
"id": "2021-01",
"title": "2021-01",
"sum": 1
},
{
"id": "2020-12",
"title": "2020-12",
"sum": 1
}
]
},
{
"id": "unique-dataset-investigations-regular",
"title": "unique-dataset-investigations-regular",
"count": 42,
"year-months": [
{
"id": "2021-09",
"title": "2021-09",
"sum": 1
},
{
"id": "2021-08",
"title": "2021-08",
"sum": 1
},
{
"id": "2021-07",
"title": "2021-07",
"sum": 1
},
{
"id": "2021-06",
"title": "2021-06",
"sum": 1
},
{
"id": "2021-05",
"title": "2021-05",
"sum": 1
},
{
"id": "2021-04",
"title": "2021-04",
"sum": 1
},
{
"id": "2021-03",
"title": "2021-03",
"sum": 1
},
{
"id": "2021-02",
"title": "2021-02",
"sum": 1
},
{
"id": "2021-01",
"title": "2021-01",
"sum": 1
},
{
"id": "2020-12",
"title": "2020-12",
"sum": 1
}
]
},
{
"id": "total-dataset-requests-regular",
"title": "total-dataset-requests-regular",
"count": 35,
"year-months": [
{
"id": "2021-09",
"title": "2021-09",
"sum": 1
},
{
"id": "2021-08",
"title": "2021-08",
"sum": 1
},
{
"id": "2021-06",
"title": "2021-06",
"sum": 1
},
{
"id": "2021-05",
"title": "2021-05",
"sum": 1
},
{
"id": "2021-04",
"title": "2021-04",
"sum": 1
},
{
"id": "2021-03",
"title": "2021-03",
"sum": 1
},
{
"id": "2021-02",
"title": "2021-02",
"sum": 1
},
{
"id": "2021-01",
"title": "2021-01",
"sum": 1
},
{
"id": "2020-12",
"title": "2020-12",
"sum": 1
},
{
"id": "2020-11",
"title": "2020-11",
"sum": 1
}
]
},
{
"id": "unique-dataset-requests-regular",
"title": "unique-dataset-requests-regular",
"count": 35,
"year-months": [
{
"id": "2021-09",
"title": "2021-09",
"sum": 1
},
{
"id": "2021-08",
"title": "2021-08",
"sum": 1
},
{
"id": "2021-06",
"title": "2021-06",
"sum": 1
},
{
"id": "2021-05",
"title": "2021-05",
"sum": 1
},
{
"id": "2021-04",
"title": "2021-04",
"sum": 1
},
{
"id": "2021-03",
"title": "2021-03",
"sum": 1
},
{
"id": "2021-02",
"title": "2021-02",
"sum": 1
},
{
"id": "2021-01",
"title": "2021-01",
"sum": 1
},
{
"id": "2020-12",
"title": "2020-12",
"sum": 1
},
{
"id": "2020-11",
"title": "2020-11",
"sum": 1
}
]
},
{
"id": "total-dataset-investigations-machine",
"title": "total-dataset-investigations-machine",
"count": 13,
"year-months": [
{
"id": "2021-08",
"title": "2021-08",
"sum": 1
},
{
"id": "2021-05",
"title": "2021-05",
"sum": 1
},
{
"id": "2021-02",
"title": "2021-02",
"sum": 1
},
{
"id": "2020-10",
"title": "2020-10",
"sum": 1
},
{
"id": "2020-07",
"title": "2020-07",
"sum": 1
},
{
"id": "2020-05",
"title": "2020-05",
"sum": 1
},
{
"id": "2019-08",
"title": "2019-08",
"sum": 1
},
{
"id": "2019-05",
"title": "2019-05",
"sum": 1
},
{
"id": "2019-03",
"title": "2019-03",
"sum": 1
},
{
"id": "2019-02",
"title": "2019-02",
"sum": 1
}
]
},
{
"id": "unique-dataset-investigations-machine",
"title": "unique-dataset-investigations-machine",
"count": 13,
"year-months": [
{
"id": "2021-08",
"title": "2021-08",
"sum": 1
},
{
"id": "2021-05",
"title": "2021-05",
"sum": 1
},
{
"id": "2021-02",
"title": "2021-02",
"sum": 1
},
{
"id": "2020-10",
"title": "2020-10",
"sum": 1
},
{
"id": "2020-07",
"title": "2020-07",
"sum": 1
},
{
"id": "2020-05",
"title": "2020-05",
"sum": 1
},
{
"id": "2019-08",
"title": "2019-08",
"sum": 1
},
{
"id": "2019-05",
"title": "2019-05",
"sum": 1
},
{
"id": "2019-03",
"title": "2019-03",
"sum": 1
},
{
"id": "2019-02",
"title": "2019-02",
"sum": 1
}
]
},
{
"id": "total-dataset-requests-machine",
"title": "total-dataset-requests-machine",
"count": 1,
"year-months": [
{
"id": "2019-08",
"title": "2019-08",
"sum": 1
}
]
},
{
"id": "unique-dataset-requests-machine",
"title": "unique-dataset-requests-machine",
"count": 1,
"year-months": [
{
"id": "2019-08",
"title": "2019-08",
"sum": 1
}
]
}
],
"registrants": [
{
"id": "datacite.cdl.ucsf",
"title": "datacite.cdl.ucsf",
"count": 182,
"years": [
{
"id": "2021",
"title": "2021",
"sum": 40
},
{
"id": "2020",
"title": "2020",
"sum": 46
},
{
"id": "2019",
"title": "2019",
"sum": 56
},
{
"id": "2018",
"title": "2018",
"sum": 40
}
]
}
]
},
"links": {
"self": "https://api.datacite.org/events?source-id=datacite-usage&doi=10.7272/q6rx997g",
"next": "https://api.datacite.org/events?doi=10.7272%2Fq6rx997g&page%5Bnumber%5D=2&page%5Bsize%5D=25&source-id=datacite-usage"
}
}
```

The`data` object is an array containing metadata for all the usage metrics for the DOI found by the query. For more information, see the [DataCite Event Data](doc:eventdata-guide) guide section on [Usage Events](doc:eventdata-guide#usage-events).

## DataCite REST API

The DataCite REST API `/dois` endpoint can be used to query DOI metadata and usage counts.

Views and downloads summarized in the following attributes of the response for a single DOI:

- `viewCount`
- `viewsOverTime`
- `downloadCount`
- `downloadsOverTime`

Example request: <https://api.datacite.org/dois/10.7272/q6rx997g>

Example response:

```json
{
  "data": {
    "id": "10.7272/q6rx997g",
    "type": "dois",
    "attributes": {
      "doi": "10.7272/q6rx997g",
      "prefix": "10.7272",
      "suffix": "q6rx997g",
      "identifiers": [],
      "alternateIdentifiers": [],
      "creators": [
        {
          "name": "Wekerle, Hartmut",
          "nameType": "Personal",
          "givenName": "Hartmut",
          "familyName": "Wekerle",
          "affiliation": [
            "Max Planck Institute of Neurobiology"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Berer, Kerstin",
          "nameType": "Personal",
          "givenName": "Kerstin",
          "familyName": "Berer",
          "affiliation": [
            "Max Planck Institute of Neurobiology"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Gerdes, Lisa Ann",
          "nameType": "Personal",
          "givenName": "Lisa Ann",
          "familyName": "Gerdes",
          "affiliation": [
            "Ludwig Maximilian University of Munich"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Cekanaviciute, Egle",
          "nameType": "Personal",
          "givenName": "Egle",
          "familyName": "Cekanaviciute",
          "affiliation": [
            "University of California, San Francisco"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Jia, Sherman",
          "nameType": "Personal",
          "givenName": "Sherman",
          "familyName": "Jia",
          "affiliation": [
            "University of California, San Francisco"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Xiao, Liang",
          "nameType": "Personal",
          "givenName": "Liang",
          "familyName": "Xiao",
          "affiliation": [
            "Beijing Genomics Institute"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Xia, Zhongkui",
          "nameType": "Personal",
          "givenName": "Zhongkui",
          "familyName": "Xia",
          "affiliation": [
            "Beijing Genomics Institute"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Liu, Chuan",
          "nameType": "Personal",
          "givenName": "Chuan",
          "familyName": "Liu",
          "affiliation": [
            "Beijing Genomics Institute"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Klotz, Luisa",
          "nameType": "Personal",
          "givenName": "Luisa",
          "familyName": "Klotz",
          "affiliation": [
            "University Hospital Münster"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Stauffer, Uta",
          "nameType": "Personal",
          "givenName": "Uta",
          "familyName": "Stauffer",
          "affiliation": [
            "Max Planck Institute of Immunobiology and Epigenetics",
            "Max Planck Institute of Immunobiology and Epigenetics"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Baranzini, Sergio",
          "nameType": "Personal",
          "givenName": "Sergio",
          "familyName": "Baranzini",
          "affiliation": [],
          "nameIdentifiers": [
            {
              "schemeUri": "https://orcid.org",
              "nameIdentifier": "https://orcid.org/0000-0003-0067-194X",
              "nameIdentifierScheme": "ORCID"
            }
          ]
        },
        {
          "name": "Kümpfel, Tania",
          "nameType": "Personal",
          "givenName": "Tania",
          "familyName": "Kümpfel",
          "affiliation": [
            "Ludwig Maximilian University of Munich"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Hohlfeld, Reinhard",
          "nameType": "Personal",
          "givenName": "Reinhard",
          "familyName": "Hohlfeld",
          "affiliation": [
            "Ludwig Maximilian University of Munich"
          ],
          "nameIdentifiers": []
        },
        {
          "name": "Krishnamoorthy, Gurumoorthy",
          "nameType": "Personal",
          "givenName": "Gurumoorthy",
          "familyName": "Krishnamoorthy",
          "affiliation": [
            "Max Planck Institute of Neurobiology"
          ],
          "nameIdentifiers": []
        }
      ],
      "titles": [
        {
          "title": "Gut Microbiota from Multiple Sclerosis patients triggers spontaneous autoimmune encephalomyelitis in mice --16S data--"
        }
      ],
      "publisher": "Dryad",
      "container": {},
      "publicationYear": 2017,
      "subjects": [
        {
          "subject": "Multiple sclerosis"
        },
        {
          "subject": "Twins"
        }
      ],
      "contributors": [],
      "dates": [
        {
          "date": "2017-10-02T07:00:00Z",
          "dateType": "Available"
        },
        {
          "date": "2017",
          "dateType": "Issued"
        }
      ],
      "language": "en",
      "types": {
        "ris": "DATA",
        "bibtex": "misc",
        "citeproc": "dataset",
        "schemaOrg": "Dataset",
        "resourceType": "dataset",
        "resourceTypeGeneral": "Dataset"
      },
      "relatedIdentifiers": [
        {
          "relationType": "IsCitedBy",
          "relatedIdentifier": "10.1073/pnas.1711233114",
          "relatedIdentifierType": "DOI"
        }
      ],
      "relatedItems": [],
      "sizes": [
        "5097529 bytes"
      ],
      "formats": [],
      "version": "2",
      "rightsList": [
        {
          "rights": "Creative Commons Attribution 4.0 International",
          "rightsUri": "https://creativecommons.org/licenses/by/4.0/legalcode",
          "schemeUri": "https://spdx.org/licenses/",
          "rightsIdentifier": "cc-by-4.0",
          "rightsIdentifierScheme": "SPDX"
        }
      ],
      "descriptions": [
        {
          "description": "The commensal microbiota has emerged as a key factor influencing human health and has been associated with several diseases, including those of the central nervous system (CNS). To investigate the role of the microbiome in multiple sclerosis (MS), a complex autoimmune disorder shaped by a multitude of genetic and environmental factors, we recruited a cohort of 34 monozygotic twin pairs discordant for MS, and compared their gut microbial composition by 16S ribosomal RNA sequencing of stool samples. While no major differences in the microbial profiles between MS-affected twins and their healthy co-twins were detected, a significant increase in some taxa (including Akkermansia) was seen in affected untreated subjects. To search for possible functional differences, we used a transgenic mouse model, in which spontaneous anti-CNS autoimmunity is dependent on the commensal gut flora. Germ-free mice colonized with microbiota from MS-affected twins, developed the MS-like disease with a significantly higher incidence than mice colonized with healthy twin-derived microbiota. Although alpha diversity was reduced compared to human donors, the microbial profiles of the colonized mice showed high intraindividual, remarkable temporal stability and a high transfer rate,. Analysis of the transplanted mouse microbiome at the level of individual taxa revealed several differences, including a significantly reduced abundance of the potentially autoimmune-protective genus Sutterella in mice colonized with MS-twin-derived microbiota. These findings provide first evidence that MS-derived microbiota contain factors that precipitate an MS-like autoimmune disease in a transgenic mouse model. This model lends itself to identify protective and pathogenic microbial component in human MS.",
          "descriptionType": "Abstract"
        },
        {
          "description": "Study design. MZ twins were recruited by launching a national televised appeal as well as internet notification in Germany with support from the German Multiple Sclerosis Society (DMSG). Inclusion criteria for study participation were met for MZ twins with an MS diagnosis according to the revised McDonald criteria or clinically isolated syndrome (CIS) in one twin only. Exclusion criteria were antibiotic, glucocorticosteroidal or immunosuppressive treatment, gastrointestinal infection or diet irregularities in the 3 months prior to study entry. In total, 34 pairs (see Table 1) visited the outpatient department at the Institute of Clinical Neuroimmunology in Munich for a detailed interview on past and present medical, family and social history, a neurological examination as well as a nutrition questionnaire. To confirm the MS diagnosis, medical records including MRI scans were obtained and reviewed. Fecal samples were either directly collected in hospital or taken at home, stored at -20°C and transferred to the hospital in cooling bags. Finally, all samples were stored at -80°C. Of all participants buccal swabs for zygosity testing were taken. The study was approved by the local Ethics Committee of the Ludwig-Maximilians University Munich and all participants gave written informed consent. 16S rRNA Sequencing and Analysis.The V3-V5 region of bacterial 16S rRNA gene was amplified using the universal forward (5’-CCGTCAATTCMTTTGAGTTT-3’) and reverse primer (5’-ACTCCTA CGGGAGGCAGCAG-3’) incorporating the FLX Titanium adapters and a unique barcode sequence. PCR products were sequenced on a 454 GS FLX titanium pyrosequencer (454 Life Sciences, Branford, CT, USA) at BGI-Shenzhen. Analysis was performed using QIIME v1.9 as described (1). Essentially, amplicon sequences were quality-filtered and grouped to operational taxonomic units (OTUs) using SortMeRNA method (2) using GreenGenes version 13.8 97% dataset for closed reference. Sequences that did not match reference sequences in the GreenGenes database were dropped from the analysis. Taxonomy was assigned to the retained OTUs based on the GreenGenes reference sequence and the GreenGenes tree was used for all downstream phylogenetic community comparisons. Samples were filtered to at least 10000 sequences per sample and OTUs were filtered to retain only OTUs present in at least 5% of samples, covering at least 0.01% of total reads. After filtering, human samples were rarefied to 10975 sequences, while mouse samples were rarefied to 8137 sequences per sample, which were the lowest number of sequences per sample, respectively. For comparison between human and mouse samples, the human and mouse datasets were combined before OTU filtering and rarefaction. The resulting OTUs were filtered as described above and samples were rarefied to 6200 sequences per sample. Alpha diversity was calculated using phylogenetic diversity index method (3). For analysis of beta diversity, pairwise distance matrices were generated by phylogenetic metric of weighted UniFrac (4) and used for PCoA. For comparison of individual taxa, samples were not rarefied. Instead, OTU abundances were normalized using variance-stabilizing transformation and taxa distributions were compared using the Wald negative binomial test from the R software package DESeq2 (as described in (4, 5) with Benjamini-Hochberg correction for multiple comparisons. All statistical analyses of differences between individual bacterial species were performed using QIIME v.1.9 or R (packages DESeq2 and phyloseq).",
          "descriptionType": "Methods"
        },
        {
          "description": "Two files are uploaded. The dataset contains both human and mice samples. Max_Planck_Twin_metadata.txt: Contains the sample metadataMax_Planck_Twin_OTU_table.txt: contains the normalized OTU abundances for each individualOTU abundances were normalized using variance-stabilizing transformation and taxa distributions were compared using the Wald negative binomial test from the R software package DESeq2 (as described in (4, 5) with Benjamini-Hochberg correction for multiple comparisons.",
          "descriptionType": "Other"
        }
      ],
      "geoLocations": [
        {
          "geoLocationBox": {
            "eastBoundLongitude": "15.04149",
            "northBoundLatitude": "55.057375",
            "southBoundLatitude": "47.270352",
            "westBoundLongitude": "5.866003"
          },
          "geoLocationPlace": "Germany",
          "geoLocationPoint": {
            "pointLatitude": "51.196755",
            "pointLongitude": "9.62743"
          }
        },
        {
          "geoLocationBox": {
            "eastBoundLongitude": "-122.35698",
            "northBoundLatitude": "37.83239",
            "southBoundLatitude": "37.70808",
            "westBoundLongitude": "-122.51489"
          },
          "geoLocationPlace": "San Francisco, CA, USA",
          "geoLocationPoint": {
            "pointLatitude": "37.778008",
            "pointLongitude": "-122.431272"
          }
        },
        {
          "geoLocationPlace": "New York, USA",
          "geoLocationPoint": {
            "pointLatitude": "43.00035",
            "pointLongitude": "-75.4999"
          }
        }
      ],
      "fundingReferences": [
        {
          "funderName": "Max-Planck-Gesellschaft",
          "awardNumber": "SFB TR-128",
          "funderIdentifier": "https://doi.org/10.13039/501100004189",
          "funderIdentifierType": "Crossref Funder ID"
        },
        {
          "funderName": "German Competence Network on Multiple Sclerosis"
        },
        {
          "funderName": "Max Planck Society",
          "funderIdentifier": "https://doi.org/10.13039/501100004189",
          "funderIdentifierType": "Crossref Funder ID"
        }
      ],
      "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPHJlc291cmNlIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhtbG5zPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtNCIgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtNCBodHRwOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC00L21ldGFkYXRhLnhzZCI+CiAgPGlkZW50aWZpZXIgaWRlbnRpZmllclR5cGU9IkRPSSI+MTAuNzI3Mi9RNlJYOTk3RzwvaWRlbnRpZmllcj4KICA8Y3JlYXRvcnM+CiAgICA8Y3JlYXRvcj4KICAgICAgPGNyZWF0b3JOYW1lPldla2VybGUsIEhhcnRtdXQ8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDNhcDJhdjUwIiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+TWF4IFBsYW5jayBJbnN0aXR1dGUgb2YgTmV1cm9iaW9sb2d5PC9hZmZpbGlhdGlvbj4KICAgIDwvY3JlYXRvcj4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+QmVyZXIsIEtlcnN0aW48L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDNhcDJhdjUwIiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+TWF4IFBsYW5jayBJbnN0aXR1dGUgb2YgTmV1cm9iaW9sb2d5PC9hZmZpbGlhdGlvbj4KICAgIDwvY3JlYXRvcj4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+R2VyZGVzLCBMaXNhIEFubjwvY3JlYXRvck5hbWU+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wNTU5MXRlNTUiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5MdWR3aWcgTWF4aW1pbGlhbiBVbml2ZXJzaXR5IG9mIE11bmljaDwvYWZmaWxpYXRpb24+CiAgICA8L2NyZWF0b3I+CiAgICA8Y3JlYXRvcj4KICAgICAgPGNyZWF0b3JOYW1lPkNla2FuYXZpY2l1dGUsIEVnbGU8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDQzbXo1ajU0IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+VW5pdmVyc2l0eSBvZiBDYWxpZm9ybmlhLCBTYW4gRnJhbmNpc2NvPC9hZmZpbGlhdGlvbj4KICAgIDwvY3JlYXRvcj4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+SmlhLCBTaGVybWFuPC9jcmVhdG9yTmFtZT4KICAgICAgPGFmZmlsaWF0aW9uIGFmZmlsaWF0aW9uSWRlbnRpZmllcj0iaHR0cHM6Ly9yb3Iub3JnLzA0M216NWo1NCIgYWZmaWxpYXRpb25JZGVudGlmaWVyU2NoZW1lPSJST1IiPlVuaXZlcnNpdHkgb2YgQ2FsaWZvcm5pYSwgU2FuIEZyYW5jaXNjbzwvYWZmaWxpYXRpb24+CiAgICA8L2NyZWF0b3I+CiAgICA8Y3JlYXRvcj4KICAgICAgPGNyZWF0b3JOYW1lPlhpYW8sIExpYW5nPC9jcmVhdG9yTmFtZT4KICAgICAgPGFmZmlsaWF0aW9uIGFmZmlsaWF0aW9uSWRlbnRpZmllcj0iaHR0cHM6Ly9yb3Iub3JnLzA0NXBuMmo5NCIgYWZmaWxpYXRpb25JZGVudGlmaWVyU2NoZW1lPSJST1IiPkJlaWppbmcgR2Vub21pY3MgSW5zdGl0dXRlPC9hZmZpbGlhdGlvbj4KICAgIDwvY3JlYXRvcj4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+WGlhLCBaaG9uZ2t1aTwvY3JlYXRvck5hbWU+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wNDVwbjJqOTQiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5CZWlqaW5nIEdlbm9taWNzIEluc3RpdHV0ZTwvYWZmaWxpYXRpb24+CiAgICA8L2NyZWF0b3I+CiAgICA8Y3JlYXRvcj4KICAgICAgPGNyZWF0b3JOYW1lPkxpdSwgQ2h1YW48L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDQ1cG4yajk0IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+QmVpamluZyBHZW5vbWljcyBJbnN0aXR1dGU8L2FmZmlsaWF0aW9uPgogICAgPC9jcmVhdG9yPgogICAgPGNyZWF0b3I+CiAgICAgIDxjcmVhdG9yTmFtZT5LbG90eiwgTHVpc2E8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDE4NTZjdzU5IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+VW5pdmVyc2l0eSBIb3NwaXRhbCBNw7xuc3RlcjwvYWZmaWxpYXRpb24+CiAgICA8L2NyZWF0b3I+CiAgICA8Y3JlYXRvcj4KICAgICAgPGNyZWF0b3JOYW1lPlN0YXVmZmVyLCBVdGE8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDU4eHphdDQ5IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+TWF4IFBsYW5jayBJbnN0aXR1dGUgb2YgSW1tdW5vYmlvbG9neSBhbmQgRXBpZ2VuZXRpY3M8L2FmZmlsaWF0aW9uPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDU4eHphdDQ5IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+TWF4IFBsYW5jayBJbnN0aXR1dGUgb2YgSW1tdW5vYmlvbG9neSBhbmQgRXBpZ2VuZXRpY3M8L2FmZmlsaWF0aW9uPgogICAgPC9jcmVhdG9yPgogICAgPGNyZWF0b3I+CiAgICAgIDxjcmVhdG9yTmFtZT5CYXJhbnppbmksIFNlcmdpbzwvY3JlYXRvck5hbWU+CiAgICAgIDxuYW1lSWRlbnRpZmllciBuYW1lSWRlbnRpZmllclNjaGVtZT0iT1JDSUQiIHNjaGVtZVVSST0iaHR0cDovL29yY2lkLm9yZy8iPjAwMDAtMDAwMy0wMDY3LTE5NFg8L25hbWVJZGVudGlmaWVyPgogICAgPC9jcmVhdG9yPgogICAgPGNyZWF0b3I+CiAgICAgIDxjcmVhdG9yTmFtZT5Lw7xtcGZlbCwgVGFuaWE8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDU1OTF0ZTU1IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+THVkd2lnIE1heGltaWxpYW4gVW5pdmVyc2l0eSBvZiBNdW5pY2g8L2FmZmlsaWF0aW9uPgogICAgPC9jcmVhdG9yPgogICAgPGNyZWF0b3I+CiAgICAgIDxjcmVhdG9yTmFtZT5Ib2hsZmVsZCwgUmVpbmhhcmQ8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDU1OTF0ZTU1IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+THVkd2lnIE1heGltaWxpYW4gVW5pdmVyc2l0eSBvZiBNdW5pY2g8L2FmZmlsaWF0aW9uPgogICAgPC9jcmVhdG9yPgogICAgPGNyZWF0b3I+CiAgICAgIDxjcmVhdG9yTmFtZT5LcmlzaG5hbW9vcnRoeSwgR3VydW1vb3J0aHk8L2NyZWF0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDNhcDJhdjUwIiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+TWF4IFBsYW5jayBJbnN0aXR1dGUgb2YgTmV1cm9iaW9sb2d5PC9hZmZpbGlhdGlvbj4KICAgIDwvY3JlYXRvcj4KICA8L2NyZWF0b3JzPgogIDx0aXRsZXM+CiAgICA8dGl0bGU+CiAgICAgIEd1dCBNaWNyb2Jpb3RhIGZyb20gTXVsdGlwbGUgU2NsZXJvc2lzIHBhdGllbnRzIHRyaWdnZXJzIHNwb250YW5lb3VzCiAgICAgIGF1dG9pbW11bmUgZW5jZXBoYWxvbXllbGl0aXMgaW4gbWljZSAtLTE2UyBkYXRhLS0KICAgIDwvdGl0bGU+CiAgPC90aXRsZXM+CiAgPHB1Ymxpc2hlcj5EcnlhZDwvcHVibGlzaGVyPgogIDxyZXNvdXJjZVR5cGUgcmVzb3VyY2VUeXBlR2VuZXJhbD0iRGF0YXNldCI+ZGF0YXNldDwvcmVzb3VyY2VUeXBlPgogIDxwdWJsaWNhdGlvblllYXI+MjAxNzwvcHVibGljYXRpb25ZZWFyPgogIDxzdWJqZWN0cz4KICAgIDxzdWJqZWN0Pk11bHRpcGxlIHNjbGVyb3Npczwvc3ViamVjdD4KICAgIDxzdWJqZWN0PlR3aW5zPC9zdWJqZWN0PgogIDwvc3ViamVjdHM+CiAgPGZ1bmRpbmdSZWZlcmVuY2VzPgogICAgPGZ1bmRpbmdSZWZlcmVuY2U+CiAgICAgIDxmdW5kZXJOYW1lPk1heC1QbGFuY2stR2VzZWxsc2NoYWZ0PC9mdW5kZXJOYW1lPgogICAgICA8ZnVuZGVySWRlbnRpZmllciBmdW5kZXJJZGVudGlmaWVyVHlwZT0iQ3Jvc3NyZWYgRnVuZGVyIElEIj5odHRwOi8vZHguZG9pLm9yZy8xMC4xMzAzOS81MDExMDAwMDQxODk8L2Z1bmRlcklkZW50aWZpZXI+CiAgICAgIDxhd2FyZE51bWJlcj5TRkIgVFItMTI4PC9hd2FyZE51bWJlcj4KICAgIDwvZnVuZGluZ1JlZmVyZW5jZT4KICAgIDxmdW5kaW5nUmVmZXJlbmNlPgogICAgICA8ZnVuZGVyTmFtZT5HZXJtYW4gQ29tcGV0ZW5jZSBOZXR3b3JrIG9uIE11bHRpcGxlIFNjbGVyb3NpczwvZnVuZGVyTmFtZT4KICAgIDwvZnVuZGluZ1JlZmVyZW5jZT4KICAgIDxmdW5kaW5nUmVmZXJlbmNlPgogICAgICA8ZnVuZGVyTmFtZT5NYXggUGxhbmNrIFNvY2lldHk8L2Z1bmRlck5hbWU+CiAgICAgIDxmdW5kZXJJZGVudGlmaWVyIGZ1bmRlcklkZW50aWZpZXJUeXBlPSJDcm9zc3JlZiBGdW5kZXIgSUQiPmh0dHA6Ly9keC5kb2kub3JnLzEwLjEzMDM5LzUwMTEwMDAwNDE4OTwvZnVuZGVySWRlbnRpZmllcj4KICAgIDwvZnVuZGluZ1JlZmVyZW5jZT4KICA8L2Z1bmRpbmdSZWZlcmVuY2VzPgogIDxkYXRlcz4KICAgIDxkYXRlIGRhdGVUeXBlPSJBdmFpbGFibGUiPjIwMTctMTAtMDJUMDc6MDA6MDBaPC9kYXRlPgogIDwvZGF0ZXM+CiAgPGxhbmd1YWdlPmVuPC9sYW5ndWFnZT4KICA8cmVsYXRlZElkZW50aWZpZXJzPgogICAgPHJlbGF0ZWRJZGVudGlmaWVyIHJlbGF0aW9uVHlwZT0iSXNDaXRlZEJ5IiByZWxhdGVkSWRlbnRpZmllclR5cGU9IkRPSSI+aHR0cHM6Ly9kb2kub3JnLzEwLjEwNzMvcG5hcy4xNzExMjMzMTE0PC9yZWxhdGVkSWRlbnRpZmllcj4KICA8L3JlbGF0ZWRJZGVudGlmaWVycz4KICA8c2l6ZXM+CiAgICA8c2l6ZT41MDk3NTI5IGJ5dGVzPC9zaXplPgogIDwvc2l6ZXM+CiAgPHZlcnNpb24+MjwvdmVyc2lvbj4KICA8cmlnaHRzTGlzdD4KICAgIDxyaWdodHMgcmlnaHRzVVJJPSJodHRwczovL2NyZWF0aXZlY29tbW9ucy5vcmcvbGljZW5zZXMvYnkvNC4wLyI+Q3JlYXRpdmUgQ29tbW9ucyBBdHRyaWJ1dGlvbiA0LjAgSW50ZXJuYXRpb25hbCAoQ0MgQlkgNC4wKTwvcmlnaHRzPgogIDwvcmlnaHRzTGlzdD4KICA8ZGVzY3JpcHRpb25zPgogICAgPGRlc2NyaXB0aW9uIGRlc2NyaXB0aW9uVHlwZT0iQWJzdHJhY3QiPgogICAgICBUaGUgY29tbWVuc2FsIG1pY3JvYmlvdGEgaGFzIGVtZXJnZWQgYXMgYSBrZXkgZmFjdG9yIGluZmx1ZW5jaW5nIGh1bWFuCiAgICAgIGhlYWx0aCBhbmQgaGFzIGJlZW4gYXNzb2NpYXRlZCB3aXRoIHNldmVyYWwgZGlzZWFzZXMsIGluY2x1ZGluZyB0aG9zZSBvZgogICAgICB0aGUgY2VudHJhbCBuZXJ2b3VzIHN5c3RlbSAoQ05TKS4gVG8gaW52ZXN0aWdhdGUgdGhlIHJvbGUgb2YgdGhlCiAgICAgIG1pY3JvYmlvbWUgaW4gbXVsdGlwbGUgc2NsZXJvc2lzIChNUyksIGEgY29tcGxleCBhdXRvaW1tdW5lIGRpc29yZGVyCiAgICAgIHNoYXBlZCBieSBhIG11bHRpdHVkZSBvZiBnZW5ldGljIGFuZCBlbnZpcm9ubWVudGFsIGZhY3RvcnMsIHdlIHJlY3J1aXRlZCBhCiAgICAgIGNvaG9ydCBvZiAzNCBtb25venlnb3RpYyB0d2luIHBhaXJzIGRpc2NvcmRhbnQgZm9yIE1TLCBhbmQgY29tcGFyZWQgdGhlaXIKICAgICAgZ3V0IG1pY3JvYmlhbCBjb21wb3NpdGlvbiBieSAxNlMgcmlib3NvbWFsIFJOQSBzZXF1ZW5jaW5nIG9mIHN0b29sCiAgICAgIHNhbXBsZXMuIFdoaWxlIG5vIG1ham9yIGRpZmZlcmVuY2VzIGluIHRoZSBtaWNyb2JpYWwgcHJvZmlsZXMgYmV0d2VlbgogICAgICBNUy1hZmZlY3RlZCB0d2lucyBhbmQgdGhlaXIgaGVhbHRoeSBjby10d2lucyB3ZXJlIGRldGVjdGVkLCBhIHNpZ25pZmljYW50CiAgICAgIGluY3JlYXNlIGluIHNvbWUgdGF4YSAoaW5jbHVkaW5nIEFra2VybWFuc2lhKSB3YXMgc2VlbiBpbiBhZmZlY3RlZAogICAgICB1bnRyZWF0ZWQgc3ViamVjdHMuIFRvIHNlYXJjaCBmb3IgcG9zc2libGUgZnVuY3Rpb25hbCBkaWZmZXJlbmNlcywgd2UgdXNlZAogICAgICBhIHRyYW5zZ2VuaWMgbW91c2UgbW9kZWwsIGluIHdoaWNoIHNwb250YW5lb3VzIGFudGktQ05TIGF1dG9pbW11bml0eSBpcwogICAgICBkZXBlbmRlbnQgb24gdGhlIGNvbW1lbnNhbCBndXQgZmxvcmEuIEdlcm0tZnJlZSBtaWNlIGNvbG9uaXplZCB3aXRoCiAgICAgIG1pY3JvYmlvdGEgZnJvbSBNUy1hZmZlY3RlZCB0d2lucywgZGV2ZWxvcGVkIHRoZSBNUy1saWtlIGRpc2Vhc2Ugd2l0aCBhCiAgICAgIHNpZ25pZmljYW50bHkgaGlnaGVyIGluY2lkZW5jZSB0aGFuIG1pY2UgY29sb25pemVkIHdpdGggaGVhbHRoeQogICAgICB0d2luLWRlcml2ZWQgbWljcm9iaW90YS4gQWx0aG91Z2ggYWxwaGEgZGl2ZXJzaXR5IHdhcyByZWR1Y2VkIGNvbXBhcmVkIHRvCiAgICAgIGh1bWFuIGRvbm9ycywgdGhlIG1pY3JvYmlhbCBwcm9maWxlcyBvZiB0aGUgY29sb25pemVkIG1pY2Ugc2hvd2VkIGhpZ2gKICAgICAgaW50cmFpbmRpdmlkdWFsLCByZW1hcmthYmxlIHRlbXBvcmFsIHN0YWJpbGl0eSBhbmQgYSBoaWdoIHRyYW5zZmVyIHJhdGUsLgogICAgICBBbmFseXNpcyBvZiB0aGUgdHJhbnNwbGFudGVkIG1vdXNlIG1pY3JvYmlvbWUgYXQgdGhlIGxldmVsIG9mIGluZGl2aWR1YWwKICAgICAgdGF4YSByZXZlYWxlZCBzZXZlcmFsIGRpZmZlcmVuY2VzLCBpbmNsdWRpbmcgYSBzaWduaWZpY2FudGx5IHJlZHVjZWQKICAgICAgYWJ1bmRhbmNlIG9mIHRoZSBwb3RlbnRpYWxseSBhdXRvaW1tdW5lLXByb3RlY3RpdmUgZ2VudXMgU3V0dGVyZWxsYSBpbgogICAgICBtaWNlIGNvbG9uaXplZCB3aXRoIE1TLXR3aW4tZGVyaXZlZCBtaWNyb2Jpb3RhLiBUaGVzZSBmaW5kaW5ncyBwcm92aWRlCiAgICAgIGZpcnN0IGV2aWRlbmNlIHRoYXQgTVMtZGVyaXZlZCBtaWNyb2Jpb3RhIGNvbnRhaW4gZmFjdG9ycyB0aGF0IHByZWNpcGl0YXRlCiAgICAgIGFuIE1TLWxpa2UgYXV0b2ltbXVuZSBkaXNlYXNlIGluIGEgdHJhbnNnZW5pYyBtb3VzZSBtb2RlbC4gVGhpcyBtb2RlbAogICAgICBsZW5kcyBpdHNlbGYgdG8gaWRlbnRpZnkgcHJvdGVjdGl2ZSBhbmQgcGF0aG9nZW5pYyBtaWNyb2JpYWwgY29tcG9uZW50IGluCiAgICAgIGh1bWFuIE1TLgogICAgPC9kZXNjcmlwdGlvbj4KICAgIDxkZXNjcmlwdGlvbiBkZXNjcmlwdGlvblR5cGU9Ik1ldGhvZHMiPgogICAgICBTdHVkeSBkZXNpZ24uIE1aIHR3aW5zIHdlcmUgcmVjcnVpdGVkIGJ5IGxhdW5jaGluZyBhIG5hdGlvbmFsIHRlbGV2aXNlZAogICAgICBhcHBlYWwgYXMgd2VsbCBhcyBpbnRlcm5ldCBub3RpZmljYXRpb24gaW4gR2VybWFueSB3aXRoIHN1cHBvcnQgZnJvbSB0aGUKICAgICAgR2VybWFuIE11bHRpcGxlIFNjbGVyb3NpcyBTb2NpZXR5IChETVNHKS4gSW5jbHVzaW9uIGNyaXRlcmlhIGZvciBzdHVkeQogICAgICBwYXJ0aWNpcGF0aW9uIHdlcmUgbWV0IGZvciBNWiB0d2lucyB3aXRoIGFuIE1TIGRpYWdub3NpcyBhY2NvcmRpbmcgdG8gdGhlCiAgICAgIHJldmlzZWQgTWNEb25hbGQgY3JpdGVyaWEgb3IgY2xpbmljYWxseSBpc29sYXRlZCBzeW5kcm9tZSAoQ0lTKSBpbiBvbmUKICAgICAgdHdpbiBvbmx5LiBFeGNsdXNpb24gY3JpdGVyaWEgd2VyZSBhbnRpYmlvdGljLCBnbHVjb2NvcnRpY29zdGVyb2lkYWwgb3IKICAgICAgaW1tdW5vc3VwcHJlc3NpdmUgdHJlYXRtZW50LCBnYXN0cm9pbnRlc3RpbmFsIGluZmVjdGlvbiBvciBkaWV0CiAgICAgIGlycmVndWxhcml0aWVzIGluIHRoZSAzIG1vbnRocyBwcmlvciB0byBzdHVkeSBlbnRyeS4gSW4gdG90YWwsIDM0IHBhaXJzCiAgICAgIChzZWUgVGFibGUgMSkgdmlzaXRlZCB0aGUgb3V0cGF0aWVudCBkZXBhcnRtZW50IGF0IHRoZSBJbnN0aXR1dGUgb2YKICAgICAgQ2xpbmljYWwgTmV1cm9pbW11bm9sb2d5IGluIE11bmljaCBmb3IgYSBkZXRhaWxlZCBpbnRlcnZpZXcgb24gcGFzdCBhbmQKICAgICAgcHJlc2VudCBtZWRpY2FsLCBmYW1pbHkgYW5kIHNvY2lhbCBoaXN0b3J5LCBhIG5ldXJvbG9naWNhbCBleGFtaW5hdGlvbiBhcwogICAgICB3ZWxsIGFzIGEgbnV0cml0aW9uIHF1ZXN0aW9ubmFpcmUuIFRvIGNvbmZpcm0gdGhlIE1TIGRpYWdub3NpcywgbWVkaWNhbAogICAgICByZWNvcmRzIGluY2x1ZGluZyBNUkkgc2NhbnMgd2VyZSBvYnRhaW5lZCBhbmQgcmV2aWV3ZWQuIEZlY2FsIHNhbXBsZXMgd2VyZQogICAgICBlaXRoZXIgZGlyZWN0bHkgY29sbGVjdGVkIGluIGhvc3BpdGFsIG9yIHRha2VuIGF0IGhvbWUsIHN0b3JlZCBhdCAtMjDCsEMKICAgICAgYW5kIHRyYW5zZmVycmVkIHRvIHRoZSBob3NwaXRhbCBpbiBjb29saW5nIGJhZ3MuIEZpbmFsbHksIGFsbCBzYW1wbGVzIHdlcmUKICAgICAgc3RvcmVkIGF0IC04MMKwQy4gT2YgYWxsIHBhcnRpY2lwYW50cyBidWNjYWwgc3dhYnMgZm9yIHp5Z29zaXR5IHRlc3RpbmcKICAgICAgd2VyZSB0YWtlbi4gVGhlIHN0dWR5IHdhcyBhcHByb3ZlZCBieSB0aGUgbG9jYWwgRXRoaWNzIENvbW1pdHRlZSBvZiB0aGUKICAgICAgTHVkd2lnLU1heGltaWxpYW5zIFVuaXZlcnNpdHkgTXVuaWNoIGFuZCBhbGwgcGFydGljaXBhbnRzIGdhdmUgd3JpdHRlbgogICAgICBpbmZvcm1lZCBjb25zZW50LiAxNlMgclJOQSBTZXF1ZW5jaW5nIGFuZCBBbmFseXNpcy5UaGUgVjMtVjUgcmVnaW9uIG9mCiAgICAgIGJhY3RlcmlhbCAxNlMgclJOQSBnZW5lIHdhcyBhbXBsaWZpZWQgdXNpbmcgdGhlIHVuaXZlcnNhbCBmb3J3YXJkCiAgICAgICg14oCZLUNDR1RDQUFUVENNVFRUR0FHVFRULTPigJkpIGFuZCByZXZlcnNlIHByaW1lciAoNeKAmS1BQ1RDQ1RBCiAgICAgIENHR0dBR0dDQUdDQUctM+KAmSkgaW5jb3Jwb3JhdGluZyB0aGUgRkxYIFRpdGFuaXVtIGFkYXB0ZXJzIGFuZCBhIHVuaXF1ZQogICAgICBiYXJjb2RlIHNlcXVlbmNlLiBQQ1IgcHJvZHVjdHMgd2VyZSBzZXF1ZW5jZWQgb24gYSA0NTQgR1MgRkxYIHRpdGFuaXVtCiAgICAgIHB5cm9zZXF1ZW5jZXIgKDQ1NCBMaWZlIFNjaWVuY2VzLCBCcmFuZm9yZCwgQ1QsIFVTQSkgYXQgQkdJLVNoZW56aGVuLgogICAgICBBbmFseXNpcyB3YXMgcGVyZm9ybWVkIHVzaW5nIFFJSU1FIHYxLjkgYXMgZGVzY3JpYmVkICgxKS4gRXNzZW50aWFsbHksCiAgICAgIGFtcGxpY29uIHNlcXVlbmNlcyB3ZXJlIHF1YWxpdHktZmlsdGVyZWQgYW5kIGdyb3VwZWQgdG8gb3BlcmF0aW9uYWwKICAgICAgdGF4b25vbWljIHVuaXRzIChPVFVzKSB1c2luZyBTb3J0TWVSTkEgbWV0aG9kICgyKSB1c2luZyBHcmVlbkdlbmVzIHZlcnNpb24KICAgICAgMTMuOCA5NyUgZGF0YXNldCBmb3IgY2xvc2VkIHJlZmVyZW5jZS4gU2VxdWVuY2VzIHRoYXQgZGlkIG5vdCBtYXRjaAogICAgICByZWZlcmVuY2Ugc2VxdWVuY2VzIGluIHRoZSBHcmVlbkdlbmVzIGRhdGFiYXNlIHdlcmUgZHJvcHBlZCBmcm9tIHRoZQogICAgICBhbmFseXNpcy4gVGF4b25vbXkgd2FzIGFzc2lnbmVkIHRvIHRoZSByZXRhaW5lZCBPVFVzIGJhc2VkIG9uIHRoZQogICAgICBHcmVlbkdlbmVzIHJlZmVyZW5jZSBzZXF1ZW5jZSBhbmQgdGhlIEdyZWVuR2VuZXMgdHJlZSB3YXMgdXNlZCBmb3IgYWxsCiAgICAgIGRvd25zdHJlYW0gcGh5bG9nZW5ldGljIGNvbW11bml0eSBjb21wYXJpc29ucy4gU2FtcGxlcyB3ZXJlIGZpbHRlcmVkIHRvIGF0CiAgICAgIGxlYXN0IDEwMDAwIHNlcXVlbmNlcyBwZXIgc2FtcGxlIGFuZCBPVFVzIHdlcmUgZmlsdGVyZWQgdG8gcmV0YWluIG9ubHkKICAgICAgT1RVcyBwcmVzZW50IGluIGF0IGxlYXN0IDUlIG9mIHNhbXBsZXMsIGNvdmVyaW5nIGF0IGxlYXN0IDAuMDElIG9mIHRvdGFsCiAgICAgIHJlYWRzLiBBZnRlciBmaWx0ZXJpbmcsIGh1bWFuIHNhbXBsZXMgd2VyZSByYXJlZmllZCB0byAxMDk3NSBzZXF1ZW5jZXMsCiAgICAgIHdoaWxlIG1vdXNlIHNhbXBsZXMgd2VyZSByYXJlZmllZCB0byA4MTM3IHNlcXVlbmNlcyBwZXIgc2FtcGxlLCB3aGljaCB3ZXJlCiAgICAgIHRoZSBsb3dlc3QgbnVtYmVyIG9mIHNlcXVlbmNlcyBwZXIgc2FtcGxlLCByZXNwZWN0aXZlbHkuIEZvciBjb21wYXJpc29uCiAgICAgIGJldHdlZW4gaHVtYW4gYW5kIG1vdXNlIHNhbXBsZXMsIHRoZSBodW1hbiBhbmQgbW91c2UgZGF0YXNldHMgd2VyZQogICAgICBjb21iaW5lZCBiZWZvcmUgT1RVIGZpbHRlcmluZyBhbmQgcmFyZWZhY3Rpb24uIFRoZSByZXN1bHRpbmcgT1RVcyB3ZXJlCiAgICAgIGZpbHRlcmVkIGFzIGRlc2NyaWJlZCBhYm92ZSBhbmQgc2FtcGxlcyB3ZXJlIHJhcmVmaWVkIHRvIDYyMDAgc2VxdWVuY2VzCiAgICAgIHBlciBzYW1wbGUuIEFscGhhIGRpdmVyc2l0eSB3YXMgY2FsY3VsYXRlZCB1c2luZyBwaHlsb2dlbmV0aWMgZGl2ZXJzaXR5CiAgICAgIGluZGV4IG1ldGhvZCAoMykuIEZvciBhbmFseXNpcyBvZiBiZXRhIGRpdmVyc2l0eSwgcGFpcndpc2UgZGlzdGFuY2UKICAgICAgbWF0cmljZXMgd2VyZSBnZW5lcmF0ZWQgYnkgcGh5bG9nZW5ldGljIG1ldHJpYyBvZiB3ZWlnaHRlZCBVbmlGcmFjICg0KSBhbmQKICAgICAgdXNlZCBmb3IgUENvQS4gRm9yIGNvbXBhcmlzb24gb2YgaW5kaXZpZHVhbCB0YXhhLCBzYW1wbGVzIHdlcmUgbm90CiAgICAgIHJhcmVmaWVkLiBJbnN0ZWFkLCBPVFUgYWJ1bmRhbmNlcyB3ZXJlIG5vcm1hbGl6ZWQgdXNpbmcKICAgICAgdmFyaWFuY2Utc3RhYmlsaXppbmcgdHJhbnNmb3JtYXRpb24gYW5kIHRheGEgZGlzdHJpYnV0aW9ucyB3ZXJlIGNvbXBhcmVkCiAgICAgIHVzaW5nIHRoZSBXYWxkIG5lZ2F0aXZlIGJpbm9taWFsIHRlc3QgZnJvbSB0aGUgUiBzb2Z0d2FyZSBwYWNrYWdlIERFU2VxMgogICAgICAoYXMgZGVzY3JpYmVkIGluICg0LCA1KSB3aXRoIEJlbmphbWluaS1Ib2NoYmVyZyBjb3JyZWN0aW9uIGZvciBtdWx0aXBsZQogICAgICBjb21wYXJpc29ucy4gQWxsIHN0YXRpc3RpY2FsIGFuYWx5c2VzIG9mIGRpZmZlcmVuY2VzIGJldHdlZW4gaW5kaXZpZHVhbAogICAgICBiYWN0ZXJpYWwgc3BlY2llcyB3ZXJlIHBlcmZvcm1lZCB1c2luZyBRSUlNRSB2LjEuOSBvciBSIChwYWNrYWdlcyBERVNlcTIKICAgICAgYW5kIHBoeWxvc2VxKS4KICAgIDwvZGVzY3JpcHRpb24+CiAgICA8ZGVzY3JpcHRpb24gZGVzY3JpcHRpb25UeXBlPSJPdGhlciI+CiAgICAgIFR3byBmaWxlcyBhcmUgdXBsb2FkZWQuIFRoZSBkYXRhc2V0IGNvbnRhaW5zIGJvdGggaHVtYW4gYW5kIG1pY2Ugc2FtcGxlcy4KICAgICAgTWF4X1BsYW5ja19Ud2luX21ldGFkYXRhLnR4dDogQ29udGFpbnMgdGhlIHNhbXBsZQogICAgICBtZXRhZGF0YU1heF9QbGFuY2tfVHdpbl9PVFVfdGFibGUudHh0OiBjb250YWlucyB0aGUgbm9ybWFsaXplZCBPVFUKICAgICAgYWJ1bmRhbmNlcyBmb3IgZWFjaCBpbmRpdmlkdWFsT1RVIGFidW5kYW5jZXMgd2VyZSBub3JtYWxpemVkIHVzaW5nCiAgICAgIHZhcmlhbmNlLXN0YWJpbGl6aW5nIHRyYW5zZm9ybWF0aW9uIGFuZCB0YXhhIGRpc3RyaWJ1dGlvbnMgd2VyZSBjb21wYXJlZAogICAgICB1c2luZyB0aGUgV2FsZCBuZWdhdGl2ZSBiaW5vbWlhbCB0ZXN0IGZyb20gdGhlIFIgc29mdHdhcmUgcGFja2FnZSBERVNlcTIKICAgICAgKGFzIGRlc2NyaWJlZCBpbiAoNCwgNSkgd2l0aCBCZW5qYW1pbmktSG9jaGJlcmcgY29ycmVjdGlvbiBmb3IgbXVsdGlwbGUKICAgICAgY29tcGFyaXNvbnMuCiAgICA8L2Rlc2NyaXB0aW9uPgogIDwvZGVzY3JpcHRpb25zPgogIDxnZW9Mb2NhdGlvbnM+CiAgICA8Z2VvTG9jYXRpb24+CiAgICAgIDxnZW9Mb2NhdGlvblBvaW50PgogICAgICAgIDxwb2ludExhdGl0dWRlPjUxLjE5Njc1NTwvcG9pbnRMYXRpdHVkZT4KICAgICAgICA8cG9pbnRMb25naXR1ZGU+OS42Mjc0MzwvcG9pbnRMb25naXR1ZGU+CiAgICAgIDwvZ2VvTG9jYXRpb25Qb2ludD4KICAgICAgPGdlb0xvY2F0aW9uQm94PgogICAgICAgIDx3ZXN0Qm91bmRMb25naXR1ZGU+NS44NjYwMDM8L3dlc3RCb3VuZExvbmdpdHVkZT4KICAgICAgICA8ZWFzdEJvdW5kTG9uZ2l0dWRlPjE1LjA0MTQ5PC9lYXN0Qm91bmRMb25naXR1ZGU+CiAgICAgICAgPHNvdXRoQm91bmRMYXRpdHVkZT40Ny4yNzAzNTI8L3NvdXRoQm91bmRMYXRpdHVkZT4KICAgICAgICA8bm9ydGhCb3VuZExhdGl0dWRlPjU1LjA1NzM3NTwvbm9ydGhCb3VuZExhdGl0dWRlPgogICAgICA8L2dlb0xvY2F0aW9uQm94PgogICAgICA8Z2VvTG9jYXRpb25QbGFjZT5HZXJtYW55PC9nZW9Mb2NhdGlvblBsYWNlPgogICAgPC9nZW9Mb2NhdGlvbj4KICAgIDxnZW9Mb2NhdGlvbj4KICAgICAgPGdlb0xvY2F0aW9uUG9pbnQ+CiAgICAgICAgPHBvaW50TGF0aXR1ZGU+MzcuNzc4MDA4PC9wb2ludExhdGl0dWRlPgogICAgICAgIDxwb2ludExvbmdpdHVkZT4tMTIyLjQzMTI3MjwvcG9pbnRMb25naXR1ZGU+CiAgICAgIDwvZ2VvTG9jYXRpb25Qb2ludD4KICAgICAgPGdlb0xvY2F0aW9uQm94PgogICAgICAgIDx3ZXN0Qm91bmRMb25naXR1ZGU+LTEyMi41MTQ4OTwvd2VzdEJvdW5kTG9uZ2l0dWRlPgogICAgICAgIDxlYXN0Qm91bmRMb25naXR1ZGU+LTEyMi4zNTY5ODwvZWFzdEJvdW5kTG9uZ2l0dWRlPgogICAgICAgIDxzb3V0aEJvdW5kTGF0aXR1ZGU+MzcuNzA4MDg8L3NvdXRoQm91bmRMYXRpdHVkZT4KICAgICAgICA8bm9ydGhCb3VuZExhdGl0dWRlPjM3LjgzMjM5PC9ub3J0aEJvdW5kTGF0aXR1ZGU+CiAgICAgIDwvZ2VvTG9jYXRpb25Cb3g+CiAgICAgIDxnZW9Mb2NhdGlvblBsYWNlPlNhbiBGcmFuY2lzY28sIENBLCBVU0E8L2dlb0xvY2F0aW9uUGxhY2U+CiAgICA8L2dlb0xvY2F0aW9uPgogICAgPGdlb0xvY2F0aW9uPgogICAgICA8Z2VvTG9jYXRpb25Qb2ludD4KICAgICAgICA8cG9pbnRMYXRpdHVkZT40My4wMDAzNTwvcG9pbnRMYXRpdHVkZT4KICAgICAgICA8cG9pbnRMb25naXR1ZGU+LTc1LjQ5OTk8L3BvaW50TG9uZ2l0dWRlPgogICAgICA8L2dlb0xvY2F0aW9uUG9pbnQ+CiAgICAgIDxnZW9Mb2NhdGlvblBsYWNlPk5ldyBZb3JrLCBVU0E8L2dlb0xvY2F0aW9uUGxhY2U+CiAgICA8L2dlb0xvY2F0aW9uPgogIDwvZ2VvTG9jYXRpb25zPgo8L3Jlc291cmNlPg==",
      "url": "http://datadryad.org/stash/dataset/doi:10.7272/Q6RX997G",
      "contentUrl": null,
      "metadataVersion": 9,
      "schemaVersion": "http://datacite.org/schema/kernel-4",
      "source": "mds",
      "isActive": true,
      "state": "findable",
      "reason": null,
      "viewCount": 730,
      "viewsOverTime": [
        {
          "yearMonth": "2018-04",
          "total": 16
        },
        {
          "yearMonth": "2018-09",
          "total": 22
        },
        {
          "yearMonth": "2018-10",
          "total": 23
        },
        {
          "yearMonth": "2018-12",
          "total": 35
        },
        {
          "yearMonth": "2019-01",
          "total": 100
        },
        {
          "yearMonth": "2019-02",
          "total": 98
        },
        {
          "yearMonth": "2019-04",
          "total": 25
        },
        {
          "yearMonth": "2019-05",
          "total": 22
        },
        {
          "yearMonth": "2019-06",
          "total": 29
        },
        {
          "yearMonth": "2019-07",
          "total": 36
        },
        {
          "yearMonth": "2019-09",
          "total": 11
        },
        {
          "yearMonth": "2019-10",
          "total": 27
        },
        {
          "yearMonth": "2020-01",
          "total": 25
        },
        {
          "yearMonth": "2020-02",
          "total": 20
        },
        {
          "yearMonth": "2020-03",
          "total": 5
        },
        {
          "yearMonth": "2020-04",
          "total": 8
        },
        {
          "yearMonth": "2020-05",
          "total": 7
        },
        {
          "yearMonth": "2020-06",
          "total": 20
        },
        {
          "yearMonth": "2020-07",
          "total": 10
        },
        {
          "yearMonth": "2020-08",
          "total": 4
        },
        {
          "yearMonth": "2020-09",
          "total": 11
        },
        {
          "yearMonth": "2020-10",
          "total": 7
        },
        {
          "yearMonth": "2020-11",
          "total": 6
        },
        {
          "yearMonth": "2020-12",
          "total": 5
        },
        {
          "yearMonth": "2021-01",
          "total": 19
        },
        {
          "yearMonth": "2021-02",
          "total": 31
        },
        {
          "yearMonth": "2021-03",
          "total": 18
        },
        {
          "yearMonth": "2021-04",
          "total": 22
        },
        {
          "yearMonth": "2021-05",
          "total": 14
        },
        {
          "yearMonth": "2021-06",
          "total": 15
        },
        {
          "yearMonth": "2021-07",
          "total": 14
        },
        {
          "yearMonth": "2021-08",
          "total": 17
        },
        {
          "yearMonth": "2021-09",
          "total": 8
        }
      ],
      "downloadCount": 91,
      "downloadsOverTime": [
        {
          "yearMonth": "2018-04",
          "total": 3
        },
        {
          "yearMonth": "2018-09",
          "total": 10
        },
        {
          "yearMonth": "2018-10",
          "total": 7
        },
        {
          "yearMonth": "2018-12",
          "total": 9
        },
        {
          "yearMonth": "2019-01",
          "total": 4
        },
        {
          "yearMonth": "2019-02",
          "total": 3
        },
        {
          "yearMonth": "2019-04",
          "total": 2
        },
        {
          "yearMonth": "2019-05",
          "total": 5
        },
        {
          "yearMonth": "2019-06",
          "total": 4
        },
        {
          "yearMonth": "2019-07",
          "total": 5
        },
        {
          "yearMonth": "2019-10",
          "total": 3
        },
        {
          "yearMonth": "2020-01",
          "total": 5
        },
        {
          "yearMonth": "2020-02",
          "total": 2
        },
        {
          "yearMonth": "2020-03",
          "total": 1
        },
        {
          "yearMonth": "2020-06",
          "total": 4
        },
        {
          "yearMonth": "2020-09",
          "total": 4
        },
        {
          "yearMonth": "2020-10",
          "total": 2
        },
        {
          "yearMonth": "2020-11",
          "total": 1
        },
        {
          "yearMonth": "2020-12",
          "total": 1
        },
        {
          "yearMonth": "2021-01",
          "total": 1
        },
        {
          "yearMonth": "2021-02",
          "total": 1
        },
        {
          "yearMonth": "2021-03",
          "total": 3
        },
        {
          "yearMonth": "2021-04",
          "total": 3
        },
        {
          "yearMonth": "2021-05",
          "total": 3
        },
        {
          "yearMonth": "2021-06",
          "total": 1
        },
        {
          "yearMonth": "2021-08",
          "total": 1
        },
        {
          "yearMonth": "2021-09",
          "total": 3
        }
      ],
      "referenceCount": 0,
      "citationCount": 1,
      "citationsOverTime": [
        {
          "year": "2022",
          "total": 1
        }
      ],
      "partCount": 0,
      "partOfCount": 0,
      "versionCount": 0,
      "versionOfCount": 0,
      "created": "2017-08-22T19:35:15.000Z",
      "registered": "2017-08-22T19:35:16.000Z",
      "published": "2017",
      "updated": "2023-02-25T16:08:18.000Z"
    },
    "relationships": {
      "client": {
        "data": {
          "id": "cdl.ucsf",
          "type": "clients"
        }
      },
      "provider": {
        "data": {
          "id": "xzvi",
          "type": "providers"
        }
      },
      "media": {
        "data": {
          "id": "10.7272/q6rx997g",
          "type": "media"
        }
      },
      "references": {
        "data": []
      },
      "citations": {
        "data": [
          {
            "id": "10.1073/pnas.1711233114",
            "type": "dois"
          }
        ]
      },
      "parts": {
        "data": []
      },
      "partOf": {
        "data": []
      },
      "versions": {
        "data": []
      },
      "versionOf": {
        "data": []
      }
    }
  }
}
```

When conducting a query using the DataCite REST API `/dois` endpoint, the total views and downloads of the query results will be aggregated by year in the `views` and `downloads` attributes of the `meta` attribute. 

> 📘 What types of usage count as views and downloads?
> 
> **Views** are counted when a usage report submitted to the [Usage Reports API](doc:usage-reports-api-guide) contains a performance instance in which:
> 
> - `metric-type` is `unique-dataset-investigations`
> - `access-method` is `regular`
> 
> **Downloads** are counted when a usage report submitted to the [Usage Reports API](doc:usage-reports-api-guide) contains a performance instance in which: 
> 
> - `metric-type` is `unique-dataset-requests`
> - `access-method` is `regular`

## Displaying Usage

You can display usage in different ways.

### DataCite Data Metrics Badge

The “Views” and "Downloads" components of the DataCite Data Metrics Badge pull the total view and download counts from the DataCite GraphQL API.

For more information, see [Displaying Usage and Citations in your Repository](displaying-usage-and-citations-in-your-repository).

### DataCite Commons

DataCite Commons displays views and downloads for DOIs.

![](https://files.readme.io/4770671-Screen_Shot_2023-04-06_at_14.14.43.png)