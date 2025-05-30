---
description: Use Hunter.io to find a person's email for a domain in a MindStudio workflow
---

# Find Email

## Configuration&#x20;

### Domain

Enter the domain that you want to use to find the email. This section can include variables.&#x20;

### Name

Enter the **first name** and **last name** of the person whose email you are searching for.&#x20;

### Output&#x20;

Save the returned data as a variable. Example: `Name_Email_1`

## Sample Output

```json
{
  "data": {
    "first_name": "Alexis",
    "last_name": "Ohanian",
    "email": "alexis@reddit.com",
    "score": 97,
    "domain": "reddit.com",
    "accept_all": false,
    "position": "Cofounder",
    "twitter": null,
    "linkedin_url": null,
    "phone_number": null,
    "company": "Reddit",
    "sources": [
      {
        "domain": "redditblog.com",
        "uri": "http://redditblog.com/2008/10/22/widgets-get-an-upgrade-and-a-firefox-extension-that-will-rock-your-world",
        "extracted_on": "2018-10-19",
        "last_seen_on": "2021-05-18",
        "still_on_page": true
      },
      ...
    ],
    "verification": {
      "date": "2021-06-14",
      "status": "valid"
    }
  },
  "meta": {
    "params": {
      "first_name": "Alexis",
      "last_name": "Ohanian",
      "full_name": null,
      "domain": "reddit.com",
      "company": null,
      "max_duration": null
    }
  }
}
```
