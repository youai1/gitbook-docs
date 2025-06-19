---
description: Get Comments data from an Instagram post in a MindStudio workflow
---

# Scrape Instagram Comments

{% embed url="https://www.youtube.com/embed/UJiudp4glUA" %}

## Configuration

### Post URL

Enter the Instagram post/reel URL you want to scrape.

This section can include variables.&#x20;

### Output Variable

Specify the name of the output variable that will store the results. Example: `Comments`

### Advanced Settings

**Result Limit:** Set the amount max amount of comments you want to scrape. The default is set to 20 comments.

### Sample Output

```json
[
  {
    "postUrl": "https://example.com/post/1",
    "id": "sample_id_1",
    "text": "Sample comment text",
    "ownerUsername": "user1",
    "ownerProfilePicUrl": "https://example.com/profile_pic.jpg",
    "timestamp": "2025-03-06T13:30:39.000Z",
    "repliesCount": 0,
    "replies": [],
    "likesCount": 32,
    "owner": {
      "fbid_v2": 12345678,
      "full_name": "John Doe",
      "id": "sample_user_id",
      "is_mentionable": false,
      "is_private": false,
      "is_verified": false,
      "username": "sample_username"
    }
  },
  {
    "postUrl": "https://example.com/post/2",
    "id": "sample_id_2",
    "text": "Another comment",
    "ownerUsername": "user2",
    "ownerProfilePicUrl": "https://example.com/profile_pic2.jpg",
    "timestamp": "2025-03-06T14:38:31.000Z",
    "repliesCount": 0,
    "replies": [],
    "likesCount": 0,
    "owner": {
      "fbid_v2": 87654321,
      "full_name": "Jane Smith",
      "id": "another_user_id",
      "is_mentionable": true,
      "is_private": false,
      "is_verified": false,
      "username": "another_username"
    }
  }
]
```
