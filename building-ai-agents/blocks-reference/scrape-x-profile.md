---
description: Get X Profile Data
---

# Scrape X Profile

The Scrape X Profile block retrieves publicly available information from a user's profile on X (formerly Twitter). Use this to enrich workflows with social data such as bio, follower count, username, and engagement metrics.

This is useful for lead enrichment, credibility checks, or contextualizing mentions from a given profile.

***

## Configurations

### Profile URL

Provide the full URL of the X user profile you want to scrape.

**Example Format:** `https://x.com/elonmusk`

{% hint style="info" %}
Only public profiles are supported. If the profile is private, suspended, or deleted, the request will return an error.
{% endhint %}

***

### Output Variable

Enter the name of the variable where the profile data will be stored.

**Example:** `profile_info`

***

## Sample Output

```json
{
  "id": "4398626122",
  "name": "OpenAI",
  "username": "OpenAI",
  "bio": "OpenAI’s mission is to ensure that artificial general intelligence benefits all of humanity. We’re hiring: https://t.co/dJGr6Lg202",
  "profileImageUrl": "https://pbs.twimg.com/profile_images/1885410181409820672/ztsaR0JW_400x400.jpg",
  "bannerImageUrl": "https://pbs.twimg.com/profile_banners/4398626122/1738590484",
  "createdAt": "Sun Dec 06 22:51:08 +0000 2015",
  "stats": {
    "followers": 4220541,
    "following": 3,
    "tweets": 1245,
    "likes": 852,
    "listed": 23991,
    "media": 350
  },
  "isVerified": true,
  "isBusiness": false,
  "url": "https://x.com/OpenAI"
}
```
