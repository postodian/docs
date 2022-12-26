# Categories

A category object can be attached to articles and makes them filterable by category. As a consequence, you can offer category pages in your blog including metadata returned by the endpoints.

## The Category Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `articlesCount` | Count of articles associated with this category. |
| `createdAt` | ISO date at which the object was created. |
| `description` | Description of the category used in meta tags. |
| `slug` | Auto-generated slug based on the title. |
| `title` | Title of the category. |
| `updatedAt` | ISO date at which the object was last modified. |

## List All Categories

Retrieves a list of category objects for your publication. Results are sorted by `title`.

### Request

```
curl -X GET https://api.postodian.com/v1/categories \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "categories": [
    {
      "id": "ViupXsm9",
      "articlesCount": 3,
      "createdAt": "2020-02-16T18:56:32.689Z",
      "description": "Vivamus accumsan sapien leo, vel tempus metus iaculis ut. Ut ultricies nulla et magna dignissim, eu lacinia lorem posuere. Ut pellentesque congue lacus, porta gravida neque varius in. Nullam viverra et arcu non pharetra.",
      "slug": "aliquam",
      "title": "Aliquam",
      "updatedAt": "2020-02-17T17:04:42.336Z"
    }
  ],
  "categoriesCount": 1,
  "hasMore": false
}
```

## Retrieve a Single Category

Retrieves a category object by its unique identifier.

### Request

```
curl -X GET https://api.postodian.com/v1/categories/:id \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "id": "ViupXsm9",
  "articlesCount": 3,
  "createdAt": "2020-02-16T18:56:32.689Z",
  "description": "Vivamus accumsan sapien leo, vel tempus metus iaculis ut. Ut ultricies nulla et magna dignissim, eu lacinia lorem posuere. Ut pellentesque congue lacus, porta gravida neque varius in. Nullam viverra et arcu non pharetra.",
  "slug": "aliquam",
  "title": "Aliquam",
  "updatedAt": "2020-02-17T17:04:42.336Z"
}
```
