---
description: Retrieve YouTube search results in a MindStudio workflow
---

# Search YouTube

## Sample Output

```json
{
  "suggestions": [
    "example studio",
    "example studios",
    "example tool",
    "example studio",
    "example studio variant",
    "example ai"
  ],
  "channels": [
    {
      "position": 3,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Example Studio",
      "link": "https://www.youtube.com/@ExampleStudio",
      "description": "Create AI solutions–simple, fast, hassle-free No expertise required",
      "subscribers": 25000,
      "thumbnail": {
        "static": "https://example.com/placeholder-thumbnail.jpg",
        "rich": "https://example.com/placeholder-thumbnail-rich.jpg"
      }
    },
    {
      "position": 14,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Example Training Studio",
      "link": "https://www.youtube.com/@examplestudio",
      "description": "Channel about training and development",
      "subscribers": 8000,
      "thumbnail": {
        "static": "https://example.com/placeholder-thumbnail.jpg",
        "rich": "https://example.com/placeholder-thumbnail-rich.jpg"
      }
    }
  ],
  "videos": [
    {
      "position": 1,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Example Studio: AI Builder Overview",
      "link": "https://www.youtube.com/watch?v=example",
      "description": "Introduction to AI building tool",
      "views": 42000,
      "channel": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "John Doe",
        "link": "https://www.youtube.com/@example",
        "thumbnail": "https://example.com/placeholder-channel-thumbnail.jpg"
      },
      "length": "7:23",
      "published_time": "1 year ago",
      "badges": ["CC"],
      "thumbnail": {
        "static": "https://example.com/placeholder-video-thumbnail.jpg",
        "rich": "https://example.com/placeholder-video-thumbnail-rich.jpg"
      }
    }
  ]
}
```
