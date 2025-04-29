---
description: Get data from an Instagram profile in a MindStudio workflow
---

# Scrape Instagram Profile

{% embed url="https://www.youtube.com/embed/w1q7vgZ6Ws4" %}

## Configuration

### Username

Enter the username or profile. URL of the profile you want to scrape.&#x20;

This section can include variables.

### Output Variable

Specify the name of the output variable that will store the results. Example: `Profile_result`

### Sample Output

```json
{
    "inputUrl": "https://example.com/profile",
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "username": "example_username",
    "url": "https://example.com/profile",
    "fullName": "John Doe",
    "biography": "Sample bio text",
    "externalUrls": [
        {
            "title": "Example Link",
            "lynx_url": "https://example.com/link",
            "url": "https://example.com/link",
            "link_type": "external"
        }
    ],
    "externalUrl": "https://example.com/link",
    "externalUrlShimmed": "https://example.com/shimmed_link",
    "followersCount": 1000,
    "followsCount": 500,
    "hasChannel": false,
    "highlightReelCount": 1,
    "isBusinessAccount": false,
    "joinedRecently": false,
    "businessCategoryName": "Content Creator",
    "private": false,
    "verified": false,
    "profilePicUrl": "https://example.com/profile_pic.jpg",
    "profilePicUrlHD": "https://example.com/profile_pic_hd.jpg",
    "igtvVideoCount": 5,
    "relatedProfiles": [
        {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "full_name": "John Doe",
            "is_private": false,
            "is_verified": false,
            "profile_pic_url": "https://example.com/profile_pic.jpg",
            "username": "example_username"
        }
    ],
    "postsCount": 100,
    "latestPosts": []
}
```
