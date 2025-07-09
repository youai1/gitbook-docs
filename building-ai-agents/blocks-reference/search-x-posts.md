---
description: Search for posts on X by keyword in a MindStudio workflow
---

# Search X Posts

{% embed url="https://www.youtube.com/embed/bOZ2-hWYucs" %}

## Configuration

### Search Query

Enter the text or keyword phrase you want to search for. You can include variables (e.g., `{{user_input}}`) to make the query dynamic.

**Example:**\
`"fact checking"`

`{{topic}} AND ("AI" OR "machine learning")`

> **Note:** You may include [X advanced search operators](https://developer.twitter.com/en/docs/twitter-api/tweets/search/integrate/build-a-query).

***

### Max Results

Set the maximum number of posts to retrieve. This can range from 10 to 100. Use the slider or type in a number.

***

### After Date _(Optional)_

Return only posts made after a specific date/time. Accepts relative expressions using `{{dateSubtract}}`, `{{currentDate}}`, or static ISO timestamps.

**Example:**

`{{dateSubtract currentDate 3 "days"}}`

This would fetch posts from the last 3 days.

***

### Before Date _(Optional)_

Return only posts made before a specific date/time. Use ISO format (`YYYY-MM-DD HH:mm:ss`).

**Example:**

`2025-07-01 00:00:00`

***

### Output Variable

Specify the variable name where the results will be saved. This variable can be used in later blocks.

**Example:**

`genAIReporting` or `Xpost_results`

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
