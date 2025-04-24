---
description: Retrieve YouTube search results in a MindStudio workflow
---

# Search YouTube

{% embed url="https://www.youtube.com/watch?v=HhABlKsq6sk" %}

## Configuration&#x20;

### Search Query

Enter the search query you want to send to Youtube. This section can include variables.

### Content Type

Select the type of content you want to return from your search. Options include:

* **Anything (default)**
* **Videos**
* **Channels**
* **Use Custom SP Filter** (for more information refer to [this article](https://serpapi.com/blog/youtube-sp-filters-paginating-sorting-and-filtering-with-the-youtube-api/))
  * You can use the Custom SP filter to filter and sort more specific types of content in your search. **Examples might include:**
    * Only searching for **4K resolution videos**
    * Only searching for videos that are **less than 4 minutes long**
  * Copy the `sp` value, and paste it in the space provided.&#x20;

### Pages

Specify the numbers of pages you want to scrape. The default will always be set to 1. The max amount of pages that can be scraped is 5.

### Output Variable&#x20;

Save the returned Youtube search data in a variable. Example: `YT_search`

### Format&#x20;

The returned Youtube video data will always be exported in **JSON**.&#x20;

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
