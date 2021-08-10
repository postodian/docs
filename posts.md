# Posts

A post object contains all relevant data required in order to display a post on your website. It also contains hydrated data of associated categories and of associated users.

We included as much data as possible to help you create SEO-friendly meta tags for a page’s head and rich display of SERP.

## The Post Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `blocks` | Array of block objects that make up the post’s content. This field is included by default if the `output` parameter is not set. |
| `categories` | Array of [category objects](https://postodian.com/docs/categories) associated with the post. |
| `cta` | Call-to-action object if attached. Defaults to `null`. |
| `createdAt` | ISO date at which the object was created. |
| `description` | Description of the post used in meta tags. |
| `html` | HTML version of the post’s content. This field is only included if the `output` parameter is set to `html`. |
| `image.hash` | Unique image file identifier (hash). |
| `image.resolutions` | Thumbnail image sources in various resolutions: `default` (730px), `160`, `350`, `540`, `1110` and `1320`. We use [imgix](https://imgix.com) for adaptive image processing and delivery. If the provided resolutions are inadequate, you can perform your own [image transformations](https://docs.imgix.com/apis/rendering) with the `image.hash`. |
| `language` | ISO 2-letter language code of the post. Defaults to the publication’s language setting. |
| `pinned` | Boolean that indicates whether the post was marked as pinned. |
| `publishedAt` | ISO date at which the post was published. |
| `slug` | Auto-generated slug based on the title. Once a post is published, it is no longer changed automatically. |
| `tags` | Array of strings by which posts can be queried. |
| `title` | Title of the post. |
| `updatedAt` | ISO date at which the object was last modified. |
| `users` | Array of [user objects](https://postodian.com/docs/users) associated with the post. |

## List All Posts

Retrieves a paginated list of published post objects. Unpublished posts (i.e. drafted or scheduled posts) cannot be retrieved.

Since the number of posts returned by this endpoint is limited to 100, it is not suitable to generate your sitemap. You can use our [sitemap endpoint](https://postodian.com/docs/sitemap) which returns all relevant fields.

### Request

```
curl -X GET https://api.postodian.com/v1/posts \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Query Parameters

| Parameter | Description |
| --- | --- |
| `excludes` <small>optional</small> | Comma-separated string of post IDs that you want to exclude from the response. Example for 3 excludes: `BbNDJTgm,b6pmUDnpX,GU_b_IeDN`. This parameter can be useful if you want to display other recent posts but wish to exclude the post that your reader is currently browsing on. |
| `limit` <small>optional</small> | A limit on the number of objects to be returned. Limit can range between 1 and 100, and the default is 20. |
| `output` <small>optional</small> | The way you would like a post’s content outputted in the response. Can be either `blocks` or `html`. Defaults to `blocks`. Read [more about blocks](https://postodian.com/docs/blocks) and our built-in HTML output. |
| `page` <small>optional</small> | Integer for the current page. |
| `sort` <small>optional</small> | The field name and order by which to sort posts. Must follow the pattern `FIELD_NAME:asc` (ascending) or `FIELD_NAME:desc` (descending). Defaults to `publishedAt:desc`, whereby posts are sorted by `publishedAt` in `desc` order. |
| `tags` <small>optional</small> | Comma-separated string of tags that posts must contain to be included in the response. Example for posts containing either of the 2 tags: `lorem,ipsum`. |

### Response

```
{
  "hasMore": false,
  "posts": [
    {
      "id": "9r8wY8PY",
      "blocks": [],
      "categories": [],
      "createdAt": "2020-02-19T22:53:15.839Z",
      "cta": null,
      "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum mattis purus enim, lobortis cursus est bibendum vitae. Aliquam molestie quis diam ac pulvinar. Aliquam congue mattis enim et aliquam.",
      "language": "en",
      "image": {
        "hash": null,
        "resolutions": {
          "default": null,
          "160": null,
          "350": null,
          "540": null,
          "1110": null,
          "1320": null
        }
      },
      "language": "en",
      "pinned": false,
      "publishedAt": "2020-03-21T12:57:00.014Z",
      "slug": "lorem-ipsum-dolor-sit-amet",
      "tags": [],
      "title": "Lorem ipsum dolor sit amet",
      "updatedAt": "2020-04-04T16:05:35.681Z",
      "users": [
        ...
      ]
    }
  ],
  "postsCount: 1
}
```

## Retrieve a Single Post

Retrieves a published post object by its unique slug. Unpublished posts (i.e. drafted or scheduled posts) cannot be retrieved.

### Request

```
curl -X GET https://api.postodian.com/v1/posts/:slug \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Query Parameters

| Parameter | Description |
| --- | --- |
| `output` <small>optional</small> | The way you would like a post’s content outputted in the response. Can be either `blocks` or `html`. Defaults to `blocks`. Read [more about blocks](https://postodian.com/docs/blocks) and our built-in HTML output. |

The `output` parameter influences what field is included in the response. By default, a `blocks` array is returned. If you set the parameter to `html`, you’ll receive an `html` field which contains a string value that was generated by our built-in HTML renderer.

Using `html` can be useful if you do not want to iterate through the blocks and generate HTML tags yourself.

### Response

```
{
  "id": "9r8wY8PY",
  "blocks": [],
  "categories": [],
  "createdAt": "2020-02-19T22:53:15.839Z",
  "cta": null,
  "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum mattis purus enim, lobortis cursus est bibendum vitae. Aliquam molestie quis diam ac pulvinar. Aliquam congue mattis enim et aliquam.",
  "language": "en",
  "image": {
    "hash": null,
    "resolutions": {
      "default": null,
      "160": null,
      "350": null,
      "540": null,
      "1110": null,
      "1320": null
    }
  },
  "language": "en",
  "pinned": false,
  "publishedAt": "2020-03-21T12:57:00.014Z",
  "slug": "lorem-ipsum-dolor-sit-amet",
  "tags": [],
  "title": "Lorem ipsum dolor sit amet",
  "updatedAt": "2020-04-04T16:05:35.681Z",
  "users": [
    ...
  ]
}
```
