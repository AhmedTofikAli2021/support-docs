---
title: Authenticating Requests with API keys
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
API keys can be used to authenticate requests, such as DOI create and update requests, when using the [DataCite REST](doc:api) and [MDS](doc:mds-api-guide) APIs. They correspond to repository accounts, share the same permissions as repository credentials, and do not expire unless revoked. You can create multiple API keys per repository account.

To create an API key, you will need repository account credentials. For more information on account types and permissions, see [Accounts in DataCite](docs:datacite-account-types).

## Create an API key

To create an API key, send an authenticated request to <https://api.datacite.org/credentials/api-keys> using the repository credentials you want to associate with the API key. Your payload must conform to the JSON:API specification and include a `name` attribute to help you identify how the key will be used.

Below is an example curl request for creating an API key. Replace the placeholder credentials with your own repository credentials and provide a descriptive `name` for your key:

```shell
curl -X POST --header 'Content-Type: application/vnd.api+json' --user YOUR_REPOSITORY_ID:YOUR_PASSWORD --data '{ "data": { "type": "apiKeys", "attributes": { "name": "Dataverse installation" } } }' 'https://api.datacite.org/credentials/api-keys'
```

The response will contain your new API key in the `key` attribute. Other attributes describing the API key are also included, like the `keyPrefix`, which contains the first 11 characters of the key:

```json
{
  "data": {
    "id": "2d36ceeb-fc94-4e88-b8b7-0b47c6c6cd67",
    "type": "apiKeys",
    "attributes": {
      "name": "Dataverse installation",
      "keyPrefix": "DC.xcmd5Zmv",
      "created": "2026-07-17T15:05:51Z",
      "updated": "2026-07-17T15:05:51Z",
      "lastUsedAt": null,
      "revokedAt": null,
      "key": "DC.xcmd5Zmv_EXAMPLE_API_KEY"
    },
    "relationships": {
      "client": {
        "data": {
          "id": "HNAJ.IAJGQC",
          "type": "clients"
        }
      }
    }
  }
}
```

> 🚧 
> 
> Keep in mind that **the complete API key will only be returned when the API key is created** and will not be visible again. Copy and store it securely for future use.

## Use an API key

API keys can be used to authenticate requests to the REST and MDS APIs. API keys can also be used in place of repository credentials in integrations. 

To authenticate a request with an API key, enter the API key as the Basic authentication username. When an API key is used, the Basic authentication password is ignored. 

Below is an example REST API request to create a DOI using the example API key created above:

```shell
curl -X POST -H "Content-Type: application/vnd.api+json" --user DC.xcmd5Zmv_EXAMPLE_API_KEY: -d @doi.json https://api.datacite.org/dois
```

### What permissions do API keys have?

API keys have the same permissions as the repository account that created them. They can be used to:

- Create and update DOI metadata using the REST and MDS APIs   
- Delete [Draft records](doc:doi-states#draft-records)  using the REST and MDS APIs   
- Access Registered and Draft state records via the [Member API](api#member-api-requires-authentication)   
- Access the “Authenticated” [rate limit tier](doc:rate-limit) 
- Access the [monthly data file](datacite-monthly-data-file) 

API keys cannot be used to: 

- Create, view, or revoke API keys  
- Modify any records except for DOIs

### When will an API key become invalid?

API keys do not expire automatically and remain valid even if your repository account password changes. An API key will only become invalid when:

- The API key is [revoked](doc:api-keys#revoke-an-api-key)  
- The corresponding repository account is deactivated or deleted

## Retrieve created API keys

To retrieve a list of the API keys created for a given repository, make a request like the following: 

```shell
curl -X GET --header 'Content-Type: application/vnd.api+json' --user YOUR_REPOSITORY_ID:YOUR_PASSWORD 'https://api.datacite.org/credentials/api-keys'
```

The response will contain a list of API keys corresponding to the repository credentials:

```json
{
  "data": [
    {
      "id": "2d36ceeb-fc94-4e88-b8b7-0b47c6c6cd67",
      "type": "apiKeys",
      "attributes": {
        "name": "Dataverse installation",
        "keyPrefix": "DC.xcmd5Zmv",
        "created": "2026-07-17T15:05:51Z",
        "updated": "2026-07-17T15:05:51Z",
        "lastUsedAt": null,
        "revokedAt": null
      },
      "relationships": {
        "client": { "data": { "id": "HNAJ.IAJGQC", "type": "clients" } }
      }
    },
    {
      "id": "0c258e1b-4bb2-4504-b923-495c1861b0ce",
      "type": "apiKeys",
      "attributes": {
        "name": "Custom script",
        "keyPrefix": "DC.RWFqc4ZA",
        "created": "2026-07-10T08:38:19Z",
        "updated": "2026-07-10T08:38:19Z",
        "lastUsedAt": null,
        "revokedAt": null
      },
      "relationships": {
        "client": { "data": { "id": "HNAJ.IAJGQC", "type": "clients" } }
      }
    }
  ],
  "meta": { "total": 2 }
}
```

Keep in mind that the list response will only contain identifying information, like the chosen `name` and the `keyPrefix` of your API keys. The complete API key is only available immediately after creation. 

### Response attribute reference

Descriptions of API key attributes are provided below: 

| Attribute                    | Description                                                        |
| :--------------------------- | :----------------------------------------------------------------- |
| id                           | Unique ID of the API key                                           |
| attributes.name              | Descriptive name chosen for the API key when it was created        |
| attributes.keyPrefix         | First 11 characters of the API key                                 |
| attributes.created           | Timestamp when the API key was created                             |
| attributes.updated           | Timestamp when the API key was updated                             |
| attributes.lastUsedAt        | Timestamp when the API key was last used to authenticate a request |
| attributes.revokedAt         | Timestamp when the API key was revoked                             |
| relationships.client.data.id | The repository account ID associated with the API key              |

### Retrieve revoked API keys

By default, the list response will not include revoked API keys. To retrieve revoked API keys, add a `include_revoked=true` parameter to the request URL: 

```shell
curl -X GET --header 'Content-Type: application/vnd.api+json' --user YOUR_REPOSITORY_ID:YOUR_PASSWORD 'https://api.datacite.org/credentials/api-keys?include_revoked=true'
```

## Revoke an API key

API keys can be revoked at any time. When an API key is revoked, it becomes invalid, loses associated repository account permissions, and cannot be reinstated.  

To revoke an API key, you need its unique `id`. You can find the `id` for the API key you want to revoke by retrieving a list of API keys as shown above.

Below is an example curl request for revoking the API key created above. Replace the `2d36ceeb-fc94-4e88-b8b7-0b47c6c6cd67` in the request URL with the `id` of the API key you would like to revoke: 

```shell
curl -X DELETE --header 'Content-Type: application/vnd.api+json' --user YOUR_REPOSITORY_ID:YOUR_PASSWORD 'https://api.datacite.org/credentials/api-keys/2d36ceeb-fc94-4e88-b8b7-0b47c6c6cd67'
```