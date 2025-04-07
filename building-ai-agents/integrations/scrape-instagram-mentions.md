---
description: Get data from mentions on Instagram in a MindStudio workflow
---

# Scrape Instagram Mentions

## Configuration

### Username

Enter the username or profile URL of the user whose mentions you want to scrape.

This section can include variables.

### Output Variable

Specify the name of the output variable that will store the results. Example: `Mentions_results`

### Advanced Settings

**Results Limit:** Set the max mentions to be returned in the result.&#x20;

### Sample Output

```json
[
  {
    "inputUrl": "https://www.instagram.com/example",
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "type": "Sidecar",
    "shortCode": "example_code",
    "caption": "Sample caption with placeholder text",
    "hashtags": ["example", "fitness", "gym"],
    "url": "https://www.instagram.com/p/example_code/",
    "commentsCount": 1,
    "dimensionsHeight": 612,
    "dimensionsWidth": 612,
    "displayUrl": "https://example.com/sample_image.jpg",
    "images": ["https://example.com/sample_image.jpg"],
    "likesCount": 3,
    "timestamp": "2025-03-06T08:53:37.000Z",
    "childPosts": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "type": "Image",
        "dimensionsHeight": 1440,
        "dimensionsWidth": 1440,
        "displayUrl": "https://example.com/sample_image.jpg",
        "timestamp": "2025-03-06T08:53:36.000Z",
        "productType": "carousel_item",
        "isSponsored": false
      }
    ],
    "ownerFullName": "John Doe",
    "ownerUsername": "example_username", 
    "ownerId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "productType": "carousel_container",
    "isSponsored": true
  }
]
```
