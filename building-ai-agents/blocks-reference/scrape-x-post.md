---
description: Get X Post Data
---

# Scrape X Post

The Scrape X Post block retrieves content from a public post on X (formerly Twitter). This allows your workflow to reference real-time data such as post text, author, timestamps, and engagement metrics for use in summaries, responses, or fact-checking.

***

## Configurations

### Post URL

Enter the full URL of the X post you'd like to scrape.

**Example Format:** `https://x.com/username/status/1234567890123456789`

{% hint style="info" %}
Only public posts are supported. Private or deleted posts will return errors.
{% endhint %}

***

### Output Variable

Specify the name of the variable where the post data will be stored.

**Example:** `post_details`

***

## Sample Output

```json
{
  "id": "1945136856297038194",
  "text": "A Chief Economist and a COO walk into a podcast...\n\n@ronniechatterji and @bradlightcap talk about the future of jobs and the economy in the age of AI on Episode 3 of the OpenAI podcast, now live. https://t.co/XhsDR1tLWn",
  "authorName": "OpenAI",
  "authorUsername": "OpenAI",
  "authorProfileImageUrl": "https://pbs.twimg.com/profile_images/1885410181409820672/ztsaR0JW_400x400.jpg",
  "isVerified": true,
  "createdAt": "Tue Jul 15 15:02:20 +0000 2025",
  "stats": {
    "replies": 135,
    "retweets": 221,
    "likes": 1376,
    "bookmarks": 647,
    "views": 892658
  },
  "url": "https://twitter.com/OpenAI/status/1945136856297038194"
}
```
