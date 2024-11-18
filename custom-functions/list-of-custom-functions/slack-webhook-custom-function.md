---
description: >-
  Build a MindStudio AI that automatically posts a summary of data to a Slack
  channel.
---

# Slack Webhook: Custom Function

## What is Slack?

[Slack](https://slack.com/) is a cloud-based team communication platform for text messaging, file sharing, voice and video calls, and group chat for team collaboration.

## What Can I Do With MindStudio and Slack?

Build a MindStudio AI that asks the app user for last quarter’s sales data in CSV format.

Automatically post a summary of that sales data to a Slack channel. Use this to keep your Sales team informed and motivated on recent sales.

## What is Required for This Custom Function?

* Slack workspace.
* Account with administrator permissions on that workspace.
* Slack channel with a [webhook](https://www.webdatarocks.com/blog/webhooks-a-complete-guide-to-understanding/) to which to send automated messages. See [Get Webhook URL for a Slack Channel](slack-webhook-custom-function.md#get-webhook-url-for-a-slack-channel).
* **Slack Webhook** Custom Function.

## Get Webhook URL for a Slack Channel

1. Navigate to the Slack channel to which to send automated messages.
2. Right-click on that channel, and then select the **View channel details** option.
3. Select the **Integrations** tab.
4. From the **App** section, select the **Add an app** button.
5. Search for, and then select, the **Incoming Webhooks** app.
6. Select the **Add to Slack** button.
7. In the **Post to Channel** drop-down menu, select which channel to post automated messages.
8. Select the **Add Incoming Webhooks Integration** button.
9. Locate the **Setup Instructions** section after the app integrates to your channel.
10. From the **Webhook URL** field, copy the webhook URL. Note this URL for the [**Slack Webhook URL** setting](slack-webhook-custom-function.md#slack-webhook-url) in MindStudio’s Slack Webhook Custom Function.
11. Select the **Save Settings** button.

## Configuration

### Slack Webhook URL

Enter the URL for your Slack channel’s webhook.

### Input

Enter the text to send to the Slack channel’s webhook. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the text. **Example:**

```
{{Input}}
```
