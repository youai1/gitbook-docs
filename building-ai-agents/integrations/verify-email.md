---
description: Use Hunter.io to verify a person's email address in a MindStudio workflow
---

# Verify Email

## Configuration&#x20;

### Email

Enter the email address that you want to verify. This section can include variables.

### Output Variable&#x20;

Save the output of the email verification to a variable. Example: `EmailVer`

## Sample Output

```json
{
  "data": {
    "status": "valid",
    "result": "deliverable",
    "_deprecation_notice": "Using result is deprecated, use status instead",
    "score": 100,
    "email": "patrick@stripe.com",
    "regexp": true,
    "gibberish": false,
    "disposable": false,
    "webmail": false,
    "mx_records": true,
    "smtp_server": true,
    "smtp_check": true,
    "accept_all": false,
    "block": false,
    "sources": [
      {
        "domain": "beta.paganresearch.io",
        "uri": "http://beta.paganresearch.io/details/stripe",
        "extracted_on": "2020-06-17",
        "last_seen_on": "2020-06-17",
        "still_on_page": true
      },
      {
        "domain": "icloudnewz.blogspot.com",
        "uri": "http://icloudnewz.blogspot.com/2017/11/follow-patrick-collison-mike-birbiglia.html",
        "extracted_on": "2020-03-25",
        "last_seen_on": "2020-06-29",
        "still_on_page": true
      }
    ]
  },
  "meta": {
    "params": {
      "email": "patrick@stripe.com"
    }
  }
}
```
