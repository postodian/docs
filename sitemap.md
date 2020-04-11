# Sitemap

This endpoint is similar to the [posts endpoint](https://postodian.com/docs/posts), but optimized for generating sitemaps as it returns the complete list of all posts with only the relevant fields.

## List All Posts

Retrieves a list of all published posts. Unpublished posts (i.e. drafted or scheduled posts) are not included.

### Request

```
curl https://api.postodian.com/v1/sitemap \
     -H "Authorization: Credential pk_febaf9ad8a2dc82a16d1d923" \
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
