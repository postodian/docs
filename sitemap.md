# Sitemap

This endpoint is similar to the [posts endpoint](https://postodian.com/docs/posts), but specifically designed for generating sitemaps. It returns the complete list of all posts with only relevant fields.

## List All Posts

Retrieves a list of all published posts. Unpublished posts (i.e. drafted or scheduled posts) are not included.

### Request

```
curl -X GET https://api.postodian.com/v1/sitemap \
     -H "X-API-KEY: pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "posts": [
    {
      "id": "9r8wY8PY",
      "categories": [],
      "slug": "lorem-ipsum-dolor-sit-amet",
      "updatedAt": "2020-04-04T16:05:35.681Z"
    }
  ],
  "postsCount": 1
}
```
