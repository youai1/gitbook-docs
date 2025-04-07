---
description: Get reels from an Instagram profile in a MindStudio workflow
---

# Scrape Instagram Reels

## Configuration

### Username

Enter the username or profile URL from which you want to scrape reels.

This section can include variables.

### Output

Specify the name of the output variable that will store the results. Example: `Reels_result`

### Advanced Settings

**Result Limit:** Set the maximum amount of reels you want to scrape. The default is set to 100.

### Sample Output

```json
[{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "type": "ReelVideo",
  "shortCode": "xxxxxxxxxx",
  "caption": "Example caption.",
  "hashtags": [],
  "mentions": [],
  "url": "https://www.example.com/reel/sample",
  "commentsCount": 333,
  "dimensionsHeight": 3000,
  "dimensionsWidth": 1690,
  "images": [
    "https://example.com/sample-image.jpg"
  ],
  "videoUrl": "https://example.com/sample-video.mp4",
  "likesCount": 22110,
  "videoViewCount": 93699,
  "timestamp": "2022-11-22T21:42:42.000Z",
  "ownerFullName": "John Doe",
  "ownerUsername": "example_user",
  "ownerId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "productType": "clips",
  "isSponsored": false,
  "videoDuration": 380.459
}]
```
