---
description: Trigger a Zap from MindStudio
---

# Zapier Webhook

The **Zapier Webhook Block** allows your AI Agent to trigger and send data to a Zapier Zap. This enables seamless integration with thousands of apps supported by Zapier — including Google Sheets, Slack, Salesforce, Gmail, and more. Ideal for pushing data out of MindStudio into external systems without writing custom code.

***

## Configurations

### Webhook URL

Enter the full webhook URL from your Zapier "Catch Hook" trigger. This is where the data payload will be sent when the block runs.

**Example:**\
`https://hooks.zapier.com/hooks/catch/123456/abcde`

To create a webhook in Zapier, choose “Webhooks by Zapier” as your trigger app and select **Catch Hook**.

***

### Data

Define the payload to send with the request using key-value pairs. You can include variables in the values to send dynamic content from earlier blocks in your workflow.

**Add a Field:**\
Use the **+ Add** button to create a new key-value pair.

**Supported Format:**

* Keys must be plain strings (e.g., `"email"`, `"subject"`).
* Values can be strings or variables (e.g., `{{user_email}}`, `{{summary_text}}`).

**Example 1: Lead Capture**

| Key      | Value            |
| -------- | ---------------- |
| `email`  | `{{user_email}}` |
| `source` | `Lead Form`      |

**Example 2: Task Creation**

| Key        | Value                    |
| ---------- | ------------------------ |
| `title`    | `{{task_name}}`          |
| `due_date` | `{{formatted_due_date}}` |

***

### Output Variable

You can store the response from the Zapier webhook (if any) in a variable for use later in the workflow.

**Example:**\
Set `Output Variable` to `zap_response` to use the returned data in another block.

***

## How It Works

1. The block sends a POST request to the configured Zapier webhook URL.
2. The defined key-value pairs are included in the body of the request.
3. If Zapier returns a response (e.g., confirmation, generated data), the response is stored in the specified output variable.
4. The workflow continues to the next connected block.

***

## Best Practices

* **Test Your Zap:** Use sample data to ensure your Zapier trigger and actions are correctly configured.
* **Use Descriptive Keys:** Make your key names easy to understand for downstream Zap steps.
* **Validate Webhook Behavior:** In Zapier, check the task history to view the payloads received from MindStudio.
* **Secure Sensitive Data:** Avoid sending sensitive information unless your Zapier endpoint and downstream apps are secure.
