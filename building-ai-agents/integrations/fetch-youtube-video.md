---
description: Fetch details from a YouTube video in a MindStudio workflow
---

# Fetch YouTube Video

{% embed url="https://www.youtube.com/watch?v=3HEoSywNVcE" %}

## Configuration&#x20;

### Video URL

Enter the URL for the Youtube video you want to fetch. This section can contain variables.&#x20;

### Output Variable&#x20;

Save the returned Youtube video data in a variable. Example: `my_video`

### Format&#x20;

The returned Youtube video data will always be exported in **JSON**.&#x20;

## Sample Output

```json
{
  "video": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "title": "Sample Music Video",
    "length_seconds": 1024,
    "views": 71936,
    "likes": 551,
    "author": "John Doe",
    "category": "Music",
    "published_time": "Jan 1, 2023",
    "description": "Sample description",
    "keywords": ["music", "sample", "video"],
    "is_family_safe": true,
    "thumbnail": "https://example.com/thumbnail.jpg"
  },
  "channel": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "John Doe",
    "link": "http://example.com",
    "subscribers": 32400,
    "thumbnail": "https://example.com/channel_thumbnail.jpg"
  },
  "comment": {
    "total": 24
  },
  "available_transcripts_languages": [
    {
      "name": "English (auto-generated)",
      "lang": "en"
    }
  ],
  "recommended_videos": {
    "videos": [
      {
        "position": 1,
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "Sample Recommended Video",
        "link": "https://example.com/video",
        "views": 846988,
        "channel": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "title": "John Doe",
          "link": "https://example.com/channel",
          "thumbnail": "https://example.com/channel_thumbnail.jpg"
        },
        "length": "10:00",
        "published_time": "1 year ago",
        "thumbnail": "https://example.com/video_thumbnail.jpg"
      }
    ]
  }
}
```
