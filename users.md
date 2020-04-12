# Users

With the `user` object, you can enrich your posts with biographical information about an author (or authors). The user object is a merge of profile information provided by the users themselves, and what you have set for the user in your publication’s user administration.

## The User Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `createdAt` | ISO date at which the object was created. This is not the timestamp at which the user signed up, but at which the user was first added to your publication. |
| `bio` | Bio with up to 1,000 characters which you can edit in your publication’s user administration. |
| `email` | Email address which you can edit in your publication’s user administration. |
| `externalId` | An external ID can be useful if you maintain your own user accounts and would like to create a reference to a user in it. |
| `image.uuid` | Picture which the user has uploaded in the profile settings. We use [Uploadcare](https://uploadcare.com) for adaptive image processing and delivery. Each uploaded file links to a unique file identifier. If the provided `image.resolutions` are inadequate, you can perform your own [image transformations](https://uploadcare.com/docs/image_transformations/) with the UUID. |
| `image.resolutions` | Thumbnail image sources in various resolutions: `default`, `low`, `medium` and `high`. |
| `name` | Name of the user. |
| `phone` | Phone number which you can edit in your publication’s user administration. |
| `postsCount` | Count of posts this user has written for the publication. |
| `profiles` | URLs to various social media profiles that the user has provided in the profile settings. |
| `slug` | Auto-generated slug based on the name. This is not necessarily unique if you have more than one user in your publication with the identical name. |
| `title` | Job title or position which you can edit in your publication’s user administration. |
| `updatedAt` | ISO date at which the object was last modified. |
| `website` | Personal website URL that the user has provided in the profile settings. |

## List All Users

Retrieves a list of user objects associated with your publication.

### Request

```
curl -X GET https://api.postodian.com/v1/users \
     -H "Authorization: Credential pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "users": [
    {
      "id": "DQfg-HWhQ",
      "bio": "Donec neque ipsum, eleifend ac augue vel, mattis sollicitudin erat. Mauris vitae purus a neque vulputate malesuada. Nullam cursus ullamcorper diam, sed pretium metus varius et. Nullam tincidunt ullamcorper mi, vitae tristique est congue ut. Integer vel dolor auctor, pretium ligula quis, placerat lectus.",
      "email": "michael@writer.com",
      "externalId": null,
      "image": {
        "uuid": null,
        "resolutions": {
          "default": null,
          "low": null,
          "medium": null,
          "high": null
        }
      },
      "name": "Michael Writer",
      "phone": null,
      "postsCount": 4,
      "profiles": {
        "instagram": null,
        "linkedin": null,
        "twitter": null
      },
      "slug": "michael-writer",
      "title": "Lead Editor",
      "website": null
    }
  ],
  "usersCount": 1
}
```

## Retrieve a Single User

Retrieves a user object by its unique identifier.

### Request

```
curl -X GET https://api.postodian.com/v1/users/:id \
     -H "Authorization: Credential pk_febaf9ad8a2dc82a16d1d923" \
```

### Response

```
{
  "id": "DQfg-HWhQ",
  "bio": "Donec neque ipsum, eleifend ac augue vel, mattis sollicitudin erat. Mauris vitae purus a neque vulputate malesuada. Nullam cursus ullamcorper diam, sed pretium metus varius et. Nullam tincidunt ullamcorper mi, vitae tristique est congue ut. Integer vel dolor auctor, pretium ligula quis, placerat lectus.",
  "email": "michael@writer.com",
  "externalId": null,
  "image": {
    "uuid": null,
    "resolutions": {
      "default": null,
      "low": null,
      "medium": null,
      "high": null
    }
  },
  "name": "Michael Writer",
  "phone": null,
  "postsCount": 4,
  "profiles": {
    "instagram": null,
    "linkedin": null,
    "twitter": null
  },
  "slug": "michael-writer",
  "title": "Lead Editor",
  "website": null
}
```
