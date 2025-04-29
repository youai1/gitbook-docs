---
description: Get posts from an Instagram profile in a MindStudio workflow
---

# Scrape Instagram Posts

{% embed url="https://www.youtube.com/embed/x-RfPtxfixI" %}

## Configuration

### Username

Enter the username or profile URL of the user whose posts you want to scrape.

### Output Variable

Specify the name of the output variable that will store the results. Example: `Posts_result`

### Advanced Settings

**Result Limit:** Set the max amount of posts you want to scrape. The default is set to 100.

**Only Posts Newer Than:** Set a date/time to limit for how far back the scraper should go. For example, if you want to only scrape posts 2 months old or newer you can type in `2 months`. To add a specific date you must use the format `YYYY-MM-DD`.

### Sample Output

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
