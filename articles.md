# Articles

An article object contains all relevant data required in order to display a article on your website. It also contains hydrated data of associated categories and of associated users.

We included as much data as possible to help you create SEO-friendly meta tags for a page’s head and rich display of SERP.

## The Article Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `action` | Call-to-action object if attached. Defaults to `null`. |
| `blocks` | Array of block objects that make up the article’s content. This field is included by default if the `output` parameter is not set. |
| `categories` | Array of [category objects](https://postodian.com/docs/categories) associated with the article. |
| `createdAt` | ISO date at which the object was created. |
| `description` | Description of the article used in meta tags. |
| `html` | HTML version of the article’s content. This field is only included if the `output` parameter is set to `html`. |
| `image.hash` | Unique image file identifier (hash). |
| `image.resolutions` | Thumbnail image sources in various resolutions: `default` (730px), `160`, `350`, `540`, `1110` and `1320`. We use [imgix](https://imgix.com) for adaptive image processing and delivery. If the provided resolutions are inadequate, you can perform your own [image transformations](https://docs.imgix.com/apis/rendering) with the `image.hash`. |
| `keywords` | Array of strings by which articles can be queried. |
| `language` | ISO 2-letter language code of the article. Defaults to the publication’s language setting. |
| `pinned` | Boolean that indicates whether the article was marked as pinned. |
| `publishedAt` | ISO date at which the article was published. |
| `slug` | Auto-generated slug based on the title. Once a article is published, it is no longer changed automatically. |
| `title` | Title of the article. |
| `updatedAt` | ISO date at which the object was last modified. |
| `users` | Array of [user objects](https://postodian.com/docs/users) associated with the article. |

## List All Articles

Retrieves a paginated list of published article objects. Unpublished articles (i.e. drafted or scheduled articles) cannot be retrieved.

Since the number of articles returned by this endpoint is limited to 100, it is not suitable to generate your sitemap. You can use our [sitemap endpoint](https://postodian.com/docs/sitemap) which returns all relevant fields.

### Request

```
curl -X GET https://api.postodian.com/v1/articles \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Query Parameters

| Parameter | Description |
| --- | --- |
| `excludes` <small>optional</small> | Comma-separated string of article IDs that you want to exclude from the response. Example for 3 excludes: `BbNDJTgm,b6pmUDnpX,GU_b_IeDN`. This parameter can be useful if you want to display other recent articles but wish to exclude the articles that your reader is currently browsing on. |
| `keywords` <small>optional</small> | Comma-separated string of keywords that articles must contain to be included in the response. Example for articles containing either of the 2 keywords: `lorem,ipsum`. |
| `limit` <small>optional</small> | A limit on the number of objects to be returned. Limit can range between 1 and 100, and the default is 20. |
| `output` <small>optional</small> | The way you would like a article’s content outputted in the response. Can be either `blocks` or `html`. Defaults to `blocks`. Read [more about blocks](https://postodian.com/docs/blocks) and our built-in HTML output. |
| `page` <small>optional</small> | Integer for the current page. |
| `sort` <small>optional</small> | The field name and order by which to sort articles. Must follow the pattern `FIELD_NAME:asc` (ascending) or `FIELD_NAME:desc` (descending). Defaults to `publishedAt:desc`, whereby articles are sorted by `publishedAt` in `desc` order. |

### Response

```
{
  "articles": [
    {
      "id": "9r8wY8PY",
      "action": null,
      "blocks": [],
      "categories": [],
      "createdAt": "2020-02-19T22:53:15.839Z",
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
      "keywords": [],
      "language": "en",
      "pinned": false,
      "publishedAt": "2020-03-21T12:57:00.014Z",
      "slug": "lorem-ipsum-dolor-sit-amet",
      "title": "Lorem ipsum dolor sit amet",
      "updatedAt": "2020-04-04T16:05:35.681Z",
      "users": [
        ...
      ]
    }
  ],
  "articlesCount: 1
  "hasMore": false,
}
```

## Retrieve a Single Article

Retrieves a published article object by its unique slug. Unpublished articles (i.e. drafted or scheduled articles) cannot be retrieved.

### Request

```
curl -X GET https://api.postodian.com/v1/articles/:slug \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Query Parameters

| Parameter | Description |
| --- | --- |
| `output` <small>optional</small> | The way you would like a article’s content outputted in the response. Can be either `blocks` or `html`. Defaults to `blocks`. Read [more about blocks](https://postodian.com/docs/blocks) and our built-in HTML output. |

The `output` parameter influences what field is included in the response. By default, a `blocks` array is returned. If you set the parameter to `html`, you’ll receive an `html` field which contains a string value that was generated by our built-in HTML renderer.

Using `html` can be useful if you do not want to iterate through the blocks and generate HTML tags yourself.

### Response

```
{
  "id": "9r8wY8PY",
  "action": null,
  "blocks": [],
  "categories": [],
  "createdAt": "2020-02-19T22:53:15.839Z",
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
  "keywords": [],
  "language": "en",
  "pinned": false,
  "publishedAt": "2020-03-21T12:57:00.014Z",
  "slug": "lorem-ipsum-dolor-sit-amet",
  "title": "Lorem ipsum dolor sit amet",
  "updatedAt": "2020-04-04T16:05:35.681Z",
  "users": [
    ...
  ]
}
```
