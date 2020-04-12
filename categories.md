# Categories

A `category` object allows you to offer blog pages specific to a category. The endpoints return relevant data with which you can generate meta tags.

## The Category Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `createdAt` | ISO date at which the object was created. |
| `description` | Description of the category used in meta tags. |
| `name` | Name of the category. |
| `postsCount` | Count of posts associated with this category. |
| `slug` | Auto-generated slug based on the name. |
| `updatedAt` | ISO date at which the object was last modified. |

## List All Categories

Retrieves a list of category objects for your publication. Results are sorted by `name`.

### Request

```
curl -X GET https://api.postodian.com/v1/categories \
     -H "Authorization: Credential pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "categories": [
    {
      "id": "ViupXsm9",
      "createdAt": "2020-02-16T18:56:32.689Z",
      "description": "Vivamus accumsan sapien leo, vel tempus metus iaculis ut. Ut ultricies nulla et magna dignissim, eu lacinia lorem posuere. Ut pellentesque congue lacus, porta gravida neque varius in. Nullam viverra et arcu non pharetra.",
      "name": "Aliquam",
      "postsCount": 3,
      "slug": "aliquam",
      "updatedAt": "2020-02-17T17:04:42.336Z"
    }
  ],
  "categoriesCount": 1
}
```

## Retrieve a Single Category

Retrieves a category object by its unique identifier.

### Request

```
curl -X GET https://api.postodian.com/v1/categories/:id \
     -H "Authorization: Credential pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "id": "ViupXsm9",
  "createdAt": "2020-02-16T18:56:32.689Z",
  "description": "Vivamus accumsan sapien leo, vel tempus metus iaculis ut. Ut ultricies nulla et magna dignissim, eu lacinia lorem posuere. Ut pellentesque congue lacus, porta gravida neque varius in. Nullam viverra et arcu non pharetra.",
  "name": "Aliquam",
  "postsCount": 3,
  "slug": "aliquam",
  "updatedAt": "2020-02-17T17:04:42.336Z"
}
```
