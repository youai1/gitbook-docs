---
description: Get general details of a Facebook page in a MindStudio workflow
---

# Scrape Facebook Page

## Configuration&#x20;

### Page URL

Enter the URL of the Facebook page you want to scrape. Only public Facebook pages and profiles can be scraped.

This section can include variables with double curly braces. Example: `{{page_URL}}`

### Output Variable

Specify the name of the output variable that will store the results. Example: `page_Result`

### Sample Output

```json
{
  "facebookUrl": "https://www.facebook.com/XXXXXXXXXXX",
  "categories": ["Page", "Reference website"],
  "info": ["XXXXXXXXXX. 78,367 likes", "878 talking about this. XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"],
  "likes": 78367,
  "messenger": null,
  "title": "XXXXXXXXXX",
  "pageId": "XXXXXXXXXXXXXXXXX",
  "pageName": "XXXXXXXXXX",
  "pageUrl": "https://www.facebook.com/XXXXXXXXXXX",
  "intro": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  "websites": ["http://www.xxxxxx.com/"],
  "email": "xxxxxxxxx@xxxxxxx.com",
  "website": "xxxxxxxxx.com",
  "followers": 77959,
  "profilePictureUrl": "https://xxxxxxx/xxxxxxxxxx.jpg",
  "coverPhotoUrl": "https://xxxxxxx/xxxxxxxxxx.jpg",
  "profilePhoto": "https://www.facebook.com/photo/?fbid=xxxxxxxx&set=a.xxxxxxxxxx",
  "creation_date": "May 28, 2010",
  "ad_status": "This Page is not currently running ads.",
  "about_me": {
    "text": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.",
    "urls": []
  },
  "facebookId": "XXXXXXXXXXXXXXXXX",
  "pageAdLibrary": {
    "is_business_page_active": false,
    "id": "xxxxxxxxxxxxxxxx"
  }
}
```
