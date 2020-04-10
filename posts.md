# Posts

A `Post` object contains all relevant data required in order to display a post on your website. It also contains hydrated data of associated categories and of associated users.

## The Post Object

| Key | Description |
| --- | --- |
| `id` | Unique identifier for the object. |
| `blocks` | Array of block objects that make up the main content of the post. |
| `categories` | Array of category objects associated with the post. |
| `createdAt` | ISO date at which the object was created. |
| `description` | Description of the post used in meta tags. |
| `image.uuid` | We use [Uploadcare](https://uploadcare.com) for adaptive image processing and delivery. Each uploaded file links to a unique file identifier. With the UUID, you can perform your own [image transformations](https://uploadcare.com/docs/image_transformations/). |
| `image.resolutions` | Image sources in various resolutions: `default`, `low`, `medium` and `high`. |
| `language` | ISO 2-letter language code of the post. Defaults to the publication’s language setting. |
| `pinned` | Boolean that indicates whether the post was marked as pinned. |
| `publishedAt` | ISO date at which the post was published. |
| `slug` | Auto-generated slug based on the title. Once a post is published, it is no longer changed automatically. |
| `status` | Status of the post. Posts are created with `draft` status. You can schedule the post of publishing upon which the status changes to `scheduled`. Once a post is public, the status becomes `published`. |
| `tags` | Array of strings by which posts can be queried. |
| `title` | Title of the post. |
| `updatedAt` | ISO date at which the object was last modified. |
| `users` | Array of user objects associated with the post. |
