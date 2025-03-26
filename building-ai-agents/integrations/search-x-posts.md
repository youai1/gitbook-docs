---
description: Search for posts on X by keyword in a MindStudio workflow
---

# Search X Posts

## Sample Output

```json
{
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "text": "RT @example: Sample tweet text about a topic.",
      "author_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "edit_history_tweet_ids": [
        "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
      ]
    },
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "text": "RT @example: Sample tweet text about indie games.",
      "author_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "edit_history_tweet_ids": [
        "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
      ]
    }
  ],
  "meta": {
    "newest_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "oldest_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "result_count": 2,
    "next_token": "example-token-string"
  }
}
```
