# Publication

The `publication` object can be useful to obtain high-level metadata about your publication, for example to use on the index page of your blog. To retrieve more granular data for your publication, such as [categories](https://postodian.com/docs/categories) or [users](https://postodian.com/docs/users), please use the respective endpoints.

## The Publication Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `active` | Boolean that indicates whether the publication is online. |
| `createdAt` | ISO date at which the object was created. |
| `description` | Description of the publication used in meta tags. |
| `language` | ISO 2-letter language code set as default language of the publication. |
| `name` | Name of the publication. |
| `updatedAt` | ISO date at which the object was last modified. |

## Retrieve a Publication

Retrieves the publication object associated with your public key.

### Request

```
curl -X GET https://api.postodian.com/v1/publication \
     -H "Authorization: Credential pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "id": "ZLpxUEupF",
  "active": true,
  "createdAt": "2020-01-31T19:43:47.862Z",
  "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum mattis purus enim, lobortis cursus est bibendum vitae. Aliquam molestie quis diam ac pulvinar. Aliquam congue mattis enim et aliquam.",
  "language": "en",
  "name": "Lorem Ipsum",
  "updatedAt": "2020-03-29T11:42:39.228Z"
}
```
