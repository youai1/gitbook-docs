---
description: Retrieve content from a Google Doc in a MindStudio workflow
---

# Fetch Google Doc

## Sample Output - JSON

```json
{
  "title": "Document Title",
  "body": {
    "content": [
      {
        "startIndex": 24,
        "endIndex": 54,
        "paragraph": {
          "elements": [
            {
              "startIndex": 24,
              "endIndex": 32,
              "textRun": {
                "content": "Invited "
              }
            },
            {
              "startIndex": 32,
              "endIndex": 33,
              "person": {
                "personProperties": {
                  "name": "John Doe",
                  "email": "example@example.com"
                }
              }
            },
            {
              "startIndex": 33,
              "endIndex": 34,
              "textRun": {
                "content": " "
              }
            },
            {
              "startIndex": 34,
              "endIndex": 35,
              "person": {
                "personProperties": {
                  "name": "John Doe",
                  "email": "example@example.com"
                }
              }
            }
          ]
        }
      },
      {
        "startIndex": 97,
        "endIndex": 641,
        "paragraph": {
          "elements": [
            {
              "startIndex": 98,
              "endIndex": 641,
              "textRun": {
                "content": "Text content."
              }
            }
          ]
        }
      }
    ]
  }
}
```

This block can also output the selected Google Doc content in **plain text**, **Markdown** or **HTML** format.
