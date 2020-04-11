# Authentication

An API key is required to authenticate requests with the Postodian API. API requests to any of the endpoints described here will fail without authentication.

You can view and manage your unique API key in your publication’s settings. You have to be the publication’s administrator in order to view the API key. There are two ways to authenticate requests.

## API Key in Query Parameters

Add your API key to every request by including `key` in the query params. When retrieving a list of your published posts, for example, your GET request could look like this:

```
https://api.postodian.com/v1/posts?key=pk_febaf9ad8a2dc82a16d1d923
```

You can see that the request URI quickly becomes illegible. You can alternatively supply your API key in your headers. See below for instructions.

## API Key in Request Headers

In your request’s headers, add a string to the `Authorization` key that containing the `Credential` method and your API key separated with a space. Example for your authorization header using a sample API key:

```
Authorization: "Credential pk_febaf9ad8a2dc82a16d1d923"
```

This method can be convenient to globally declare an authorization header for your entire app. Supplying your API key in each query params will become redundant.
