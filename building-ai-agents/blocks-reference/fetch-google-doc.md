---
description: Retrieve content from a Google Doc in a MindStudio workflow
---

# Fetch Google Doc

## Configuration

### Account&#x20;

#### Dynamic (Ask at runtime)

This setting will ask a user to login to their Google Drive account when they run the app.

#### Connect a New Account

Follow the instructions on the pop-up window to directly connect MindStudio to your Google Drive account.&#x20;

### Document&#x20;

Add the document URL for the document you want to fetch. If you have connected your Google Drive account, you can search for your document by selecting the **search folder icon** next to the text field.&#x20;

This section can include variables.&#x20;

### Export Format

Select the format you want the document contents exported as. Options include:

* **Plain Text**&#x20;
* **Markdown**&#x20;
* **HTML**
* **JSON (Google Doc Format)**

### Output Variable&#x20;

Save the contents of the fetched document to a variable. Example: `Doc_fetch_1`

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
