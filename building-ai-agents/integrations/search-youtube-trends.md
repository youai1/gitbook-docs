---
description: Search for trends by a specified category in a MindStudio workflow
---

# Search YouTube Trends

{% embed url="https://www.youtube.com/embed/5_uY3QHJCdI" %}

## Configuration&#x20;

### Category&#x20;

Specify the trend category you want to search. The options include:

* **Now (default)**
* **Music**&#x20;
* **Gaming**
* **Films**

### Country&#x20;

Select the country of origin you want to use. United States is chosen by default. For the full list of supported countries [look here. ](https://www.searchapi.io/docs/parameters/youtube/gl)

### Language&#x20;

Specify the language you want you want use. English is selected by default. For the full list of supported languages [look here. ](https://www.searchapi.io/docs/parameters/youtube/hl)

### Output Variable&#x20;

Save the returned data as a variable. Example: `Trends_Return`

## Sample Output

```json
{
  "trending": [
    {
      "position": 1,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Sample Video Title",
      "link": "https://www.youtube.com/watch?v=example",
      "views": 3142370,
      "channel": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "John Doe Channel",
        "link": "https://www.youtube.com/@example",
        "is_verified": true,
        "thumbnail": "https://example.com/thumbnail.jpg"
      },
      "length": "2:00:11",
      "published_time": "Streamed recently",
      "thumbnail": "https://example.com/video_thumbnail.jpg"
    }
  ],
  "recently_trending": [
    {
      "position": 1,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Sample Trending Video",
      "link": "https://www.youtube.com/watch?v=example",
      "views": 11472521,
      "channel": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "John Doe Pictures",
        "link": "https://www.youtube.com/@example",
        "is_verified": true,
        "thumbnail": "https://example.com/channel_thumbnail.jpg"
      },
      "length": "0:28",
      "published_time": "7 days ago",
      "thumbnail": "https://example.com/trending_thumbnail.jpg"
    }
  ],
  "shorts": [
    {
      "position": 1,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Sample Short Video",
      "link": "https://www.youtube.com/shorts/example",
      "views": 3500000,
      "thumbnail": "https://example.com/shorts_thumbnail.jpg"
    }
  ],
  "featured_artist_videos": [
    {
      "position": 1,
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "Sample Artist Video",
      "link": "https://www.youtube.com/watch?v=example",
      "views": 8791803,
      "channel": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "John Doe Artist",
        "link": "https://www.youtube.com/channel/example",
        "thumbnail": "https://example.com/artist_thumbnail.jpg"
      },
      "length": "3:06",
      "published_time": "1 month ago",
      "thumbnail": "https://example.com/artist_video_thumbnail.jpg"
    }
  ]
}
```
