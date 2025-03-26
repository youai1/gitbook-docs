---
description: Use Hunter.io to find emails for a given website in a MindStudio workflow
---

# Domain Search

## Sample Output

```json

  "data": {
    "domain": "intercom.com",
    "disposable": false,
    "webmail": false,
    "accept_all": true,
    "pattern": "{first}",
    "organization": "Intercom",
    "description": "Faster resolutions, higher CSAT, and lighter support volumes with the only platform to combine the power of automation and human customer support.",
    "industry": "Software Development",
    "twitter": null,
    "facebook": null,
    "linkedin": null,
    "instagram": null,
    "youtube": null,
    "technologies": ["amazon-web-services", "facebook", "intercom", "marketo", "node-js", "react", "recaptcha", "sentry"],
    "country": null,
    "state": null,
    "city": null,
    "postal_code": null,
    "street": null,
    "headcount": "501-1000",
    "company_type": "Educational Institution",
    "emails": [
      {
        "value": "ciaran@intercom.com",
        "type": "personal",
        "confidence": 92,
        "sources": [
          {
            "domain": "github.com",
            "uri": "http://github.com/ciaranlee",
            "extracted_on": "2015-07-29",
            "last_seen_on": "2017-07-01",
            "still_on_page": true
          },
          {
            "domain": "blog.intercom.com",
            "uri": "http://blog.intercom.com/were-hiring-a-support-engineer/",
            "extracted_on": "2015-08-29",
            "last_seen_on": "2017-07-01",
            "still_on_page": true
          },
          ...
        ],
        "first_name": "Ciaran",
        "last_name": "Lee",
        "position": "Support Engineer",
        "position_raw": "Support Engineer",
        "seniority": "senior",
        "department": "it",
        "linkedin": null,
        "twitter": "ciaran_lee",
        "phone_number": null,
        "verification": {
          "date": "2019-12-06",
          "status": "valid"
        }
      },
      ...
    ],
    "linked_domains": []
  },
  "meta": {
    "results": 35,
    "limit": 10,
    "offset": 0,
    "params": {
      "domain": "intercom.com",
      "company": null,
      "type": null,
      "seniority": null,
      "department": null
    }
  }
}
```
