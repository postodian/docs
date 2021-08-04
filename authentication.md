# Authentication

The Postodian API requires an API key to authenticate requests. API requests to any of the endpoints described here will fail without authentication.

You can view and manage your unique API key in your publication’s settings. You have to be the publication’s administrator in order to view the API key.

## API Key in Request Headers

Pass your API key into the `X-API-KEY` header. Example for your request using a sample public key:

```
"X-API-KEY": "pk_febaf9ad8a2dc82a16d1d923"
```

This method can be convenient to globally declare an authorization header for your entire app. Supplying your API key in each query params will become redundant.
