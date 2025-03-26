---
description: Get posts from an Instagram profile in a MindStudio workflow
---

# Scrape Instagram Posts

## Sample Output

```json
[{
  "queryUsername": "example_username",
  "position": 1,
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "type": "Image",
  "shortCode": "example_code",
  "caption": "Sample caption text with obfuscated details.",
  "hashtags": [],
  "mentions": [
    "example_mention"
  ],
  "url": "https://www.instagram.com/p/example_post/",
  "commentsCount": 96,
  "firstComment": "",
  "latestComments": [],
  "dimensionsHeight": 720,
  "dimensionsWidth": 1080,
  "displayUrl": "https://example.com/sample_image.jpg",
  "images": [],
  "alt": null,
  "likesCount": 5000,
  "timestamp": "2022-01-01T00:00:00.000Z",
  "childPosts": [],
  "locationName": null,
  "locationId": null,
  "ownerFullName": null,
  "ownerUsername": "example_username",
  "ownerId": "xxxxxxxxxx"
},
{
  "queryUsername": "example_username",
  "position": 2,
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "type": "Sidecar",
  "shortCode": "example_code",
  "caption": "Sample caption text with obfuscated details.",
  "hashtags": [],
  "mentions": [],
  "url": "https://www.instagram.com/p/example_post/",
  "commentsCount": 2000,
  "firstComment": "",
  "latestComments": [],
  "dimensionsHeight": 498,
  "dimensionsWidth": 750
}]
```
