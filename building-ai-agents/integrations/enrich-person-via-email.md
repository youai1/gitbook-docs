---
description: Use Hunter.io to enrich person's data via email in a MindStudio workflow
---

# Enrich Person via Email

## Configuration&#x20;

### Email

Enter the email for person whose data you want to enrich. This section can include variables.

### Output

Save the enriched data to a variable. Example: `personName_Enriched`

## Sample Output

```json

  "data": {
    "id": "16210bd7-67c0-5b56-ba90-aa80ed9395a8",
    "name": {
      "fullName": "François Grante",
      "givenName": "François",
      "familyName": "Grante"
    },
    "email": "francois@hunter.io",
    "location": "Tokyo, Japan",
    "timeZone": "Asia/Tokyo",
    "utcOffset": 9,
    "geo": {
      "city": "Tokyo",
      "state": null,
      "stateCode": null,
      "country": "Japan",
      "countryCode": "JP",
      "lat": 35.6895,
      "lng": 139.69171
    },
    "bio": null,
    "site": null,
    "avatar": null,
    "employment": {
      "domain": "hunter.io",
      "name": "Hunter",
      "title": "Co-Founder",
      "role": "executive",
      "subRole": null,
      "seniority": null
    },
    "facebook": {
      "handle": null
    },
    "github": {
      "handle": null,
      "id": null,
      "avatar": null,
      "company": null,
      "blog": null,
      "followers": null,
      "following": null
    },
    "twitter": {
      "handle": "fgrante",
      "id": null,
      "bio": null,
      "followers": null,
      "following": null,
      "statuses": null,
      "favorites": null,
      "location": null,
      "site": null,
      "avatar": null
    },
    "linkedin": {
      "handle": "fran%c3%a7ois-grante-028a364a"
    },
    "googleplus": {
      "handle": null
    },
    "gravatar": {
      "handle": null,
      "urls": [],
      "avatar": null,
      "avatars": []
    },
    "fuzzy": false,
    "emailProvider": "google.com",
    "indexedAt": "2024-12-11",
    "phone": null,
    "activeAt": "2024-12-11",
    "inactiveAt": null
  },
  "meta": {
    "email": "francois@hunter.io"
  }
}
```
