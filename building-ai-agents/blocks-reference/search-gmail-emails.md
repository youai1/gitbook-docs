---
description: Retrieve Gmail search results in a MindStudio workflow
hidden: true
---

# Search Gmail Emails

## Sample Output - Plain Text

```json
From: Company Notifications <notifications@example.com>
To: example@example.com
Date: Thu, 06 Mar 2025 18:39:51 +0000
Subject: Welcome to Platform!

[Email body]

The Team

© 2025 Copyright Company INC. 
123 Example Street
EIN: 000000000
```

## Sample Output - JSON

```json
[
  {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "subject": "Welcome to MindStudio!",
    "from": "MindStudio <notifications@example.com>",
    "to": "example@example.com", 
    "date": "Thu, 06 Mar 2025 18:39:51 +0000",
    "plainBody": "Sample plain text body",
    "htmlBody": "Sample HTML email content",
    "labels": ["CATEGORY_UPDATES", "INBOX"]
  },
  {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", 
    "subject": "Join \"Example Organization\" on MindStudio",
    "from": "MindStudio <noreply@example.com>",
    "to": "example@example.com",
    "date": "Thu, 06 Mar 2025 18:38:45 +0000 (UTC)",
    "plainBody": "",
    "htmlBody": "Sample HTML email content",
    "labels": ["CATEGORY_UPDATES", "INBOX"]
  }
]
```
