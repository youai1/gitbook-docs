---
description: Fetch details from a YouTube channel in a MindStudio workflow
---

# Fetch YouTube Channel

{% embed url="https://www.youtube.com/embed/eNgrF08DjjU" %}

## Configuration&#x20;

### Channel URL

Enter the URL for the Youtube channel that you want to fetch. This section can include variables.&#x20;

### Output Variable&#x20;

Save the channel data to a variable. Example: `YTchannel_data`

### Format

The Youtube channel data will always be exported in **JSON**.

## Sample Output

```json
{
  "about": {
    "description": "One word. Here you'll find a 360-degree approach that weaves together the mental, physical, spiritual, emotional, and environmental aspects of well-being.",
    "subscribers": 168000,
    "videos": 770,
    "views": 12436659,
    "joined_date": "2010-01-31",
    "joined_date_text": "Joined Jan 31, 2010",
    "country": "United States",
    "links": [
      {
        "title": "Example Website",
        "link": "http://www.example.com/"
      },
      {
        "title": "Newsletters",
        "link": "https://www.example.com/newsletters"
      },
      {
        "title": "Social Media",
        "link": "https://www.instagram.com/example/"
      },
      {
        "title": "Social Platform",
        "link": "https://www.tiktok.com/@example"
      }
    ]
  },
  "channel": {
    "handle": "@example",
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "title": "Example Podcast",
    "subscribers": 168000,
    "videos": 770,
    "description": "Generic description of wellness approach.",
    "keywords": "wellness health example",
    "tags": ["wellness", "health", "example"],
    "available_countries": ["US"],
    "first_link": "http://www.example.com/",
    "is_family_safe": true,
    "banner": "https://example.com/banner.jpg",
    "avatar": "https://example.com/avatar.jpg"
  },
  "highlighted_video": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "title": "Example Podcast Episode",
    "link": "https://www.youtube.com/watch?v=example",
    "description": "Sample podcast description",
    "external_links": ["https://example.com"],
    "views": 92958,
    "published_time": "10 months ago"
  }
}
```
