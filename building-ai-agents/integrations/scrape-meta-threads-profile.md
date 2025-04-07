---
description: Get data from a Meta Threads profile in a MindStudio workflow
---

# Scrape Meta Threads Profile

## Configuration

### Username

Enter the username or profile URL of the Threads profile you want to scrape.

This section can include variables.

### Output Variable

Specify the name of the output variable that will store the results. Example: `Threads_result`

### Sample Output

```json
{
  "url": "https://www.example.com/profile",
  "is_private": false,
  "pk": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "text_post_app_is_private": false,
  "friendship_status": null,
  "profile_pic_url": "https://example.com/profile_pic.jpg",
  "username": "example_user",
  "text_post_app_remove_mention_entrypoint": null,
  "show_text_post_app_replies_tab": true,
  "gating": null,
  "follower_count": 50000,
  "profile_context_facepile_users": null,
  "hd_profile_pic_versions": [
    {
      "height": 320,
      "url": "https://example.com/profile_pic_320.jpg",
      "width": 320
    }
  ],
  "is_verified": true,
  "biography": "Sample bio description",
  "text_app_biography": {
    "text_fragments": {
      "fragments": [
        {
          "fragment_type": "plaintext",
          "plaintext": "Sample biography text"
        }
      ]
    }
  },
  "full_name": "John Doe",
  "bio_links": [
    {
      "url": "https://example.com",
      "is_verified": false,
      "link_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
    }
  ],
  "transparency_label": null,
  "is_threads_only_user": false,
  "show_text_post_app_badge": true,
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "latestPosts": [
    {
      "id": "sample_post_id",
      "pk": "sample_pk",
      "caption": {
        "text": "Sample post caption",
        "pk": "sample_caption_pk"
      }
    }
  ]
}
```
