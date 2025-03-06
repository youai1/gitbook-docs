---
description: Search for posts on Bluesky in a MindStudio Workflow
---

# Search Bluesky Posts

## Sample Output

```json
{
  "posts": [
    {
      "uri": "at://did:plc:xxxxxxxxxxxxxx/app.bsky.feed.post/xxxxxx",
      "cid": "bafyreixxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
      "author": {
        "did": "did:plc:xxxxxxxxxxxxxx",
        "handle": "xxxxx.bsky.social",
        "displayName": "xxxxx",
        "avatar": "https://cdn.bsky.app/img/avatar/plain/did:plc:xxxxxxxxxxxxxx/bafkreixxxxxxxxxxxxxxxxxxxxxx@jpeg",
        "labels": [],
        "createdAt": "2025-01-20T10:53:19.743Z"
      },
      "record": {
        "$type": "app.bsky.feed.post",
        "createdAt": "2025-03-04T08:18:50.233Z",
        "embed": {
          "$type": "app.bsky.embed.images",
          "images": [
            {
              "alt": "",
              "aspectRatio": {
                "height": 1350,
                "width": 1080
              },
              "image": {
                "$type": "blob",
                "ref": {
                  "$link": "bafkreixxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
                },
                "mimeType": "image/png",
                "size": 483205
              }
            }
          ]
        },
        "facets": [
          {
            "features": [
              {
                "$type": "app.bsky.richtext.facet#link",
                "uri": "https://vist.ly/xxxxxx"
              }
            ],
            "index": {
              "byteEnd": 277,
              "byteStart": 254
            }
          }
        ],
        "text": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx https://vist.ly/xxxxxx \n#BusinessSolutions #xxxxxxxxx"
      },
      "embed": {
        "$type": "app.bsky.embed.images#view",
        "images": [
          {
            "thumb": "https://cdn.bsky.app/img/feed_thumbnail/plain/did:plc:xxxxxxxxxxxxxx/bafkreixxxxxxxxxxxxxxxxxxxxxx@jpeg",
            "fullsize": "https://cdn.bsky.app/img/feed_fullsize/plain/did:plc:xxxxxxxxxxxxxx/bafkreixxxxxxxxxxxxxxxxxxxxxx@jpeg",
            "alt": "",
            "aspectRatio": {
              "height": 1350,
              "width": 1080
            }
          }
        ]
      },
      "replyCount": 1,
      "repostCount": 0,
      "likeCount": 1,
      "quoteCount": 0,
      "indexedAt": "2025-03-04T08:18:54.853Z",
      "labels": []
    }
  ]
}
```
