---
description: Extract text content from a file provided via a URL
---

# Extract Text from File Block

The **Extract Text from File Block** allows you to extract text content from a file provided via a URL. This block is perfect for workflows that require processing text from uploaded files or external sources.

## **Configurations**

### **URL**

Provide the URL of the file to extract text from. You can enter the URL directly or use a `{{variable}}` to make it dynamic.

**Example:**

* Static URL: **`https://example.com/document.pdf`**
* Dynamic URL: **`{{file_url}}`**

#### **Supported File Types**

* Plain Text (.txt, .md)
* HTML (.html)
* JSON (.json)
* PDF Document (.pdf)
* Spreadsheet (.csv, .xlsx)
* Word Document (.docx)

#### **File Size Limits**

The maximum file size is **10MB**.

### **Output Variable**

Creates a new variable and saves the extracted text to it. Enter a `variable_name` to store the response for later use in the workflow.

***

## Best Practices

* **Validate File URLs**: Ensure the provided URL points to a valid file with readable text content.
* **Use Variables**: Leverage dynamic variables to adapt the block to multiple use cases without manually changing the URL.
* **Set Clear Outputs**: Choose meaningful variable names to make workflow debugging and customization easier.
* **Monitor File Size**: Keep file sizes within the 10MB limit to ensure smooth processing.
