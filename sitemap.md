# Sitemap

This endpoint is similar to the [articles endpoint](https://postodian.com/docs/articles), but specifically designed for generating sitemaps. It returns the complete list of all articles with only relevant fields.

## List All Articles

Retrieves a list of all published articles. Unpublished articles (i.e. drafted or scheduled articles) are not included.

### Request

```
curl -X GET https://api.postodian.com/v1/sitemap \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "articles": [
    {
      "id": "9r8wY8PY",
      "categories": [],
      "slug": "lorem-ipsum-dolor-sit-amet",
      "updatedAt": "2020-04-04T16:05:35.681Z"
    }
  ],
  "articlesCount": 1
}
```
