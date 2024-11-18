---
description: >-
  Build a MindStudio AI that automatically post a summary of that blog article
  to a Discord channel.
---

# Discord Webhook: Custom Function

## What is Discord?

[Discord](https://discord.com/) is a cloud-based instant messaging and VoIP social platform for communication through voice calls, video calls, text messaging, and media and files.

## What Can I Do With MindStudio and Discord?

Build a MindStudio AI that asks the app user for a URL of a blog article.

Automatically post a summary of that blog article to a Discord channel. Use this to keep your Discord community up to date on current trends and interests.

## What is Required for This Custom Function?

* Discord account with administrator permissions to a Discord server.
* Discord channel with a [webhook](https://www.webdatarocks.com/blog/webhooks-a-complete-guide-to-understanding/) to which to send automated messages. See [Get Webhook URL for a Discord Channel](discord-webhook-custom-function.md#get-webhook-url-for-a-discord-channel).
* **Discord Webhook** Custom Function.

## Get Webhook URL for a Discord Channel

1. Locate or create the Discord channel to send automated messages.
2. Select the **Edit Channel** icon.
3. Select the **Integrations** section on the left-side panel.
4. Select the **Create Webhook** button.
5. Expand the newly created webhook.
6. Select the **Copy Webhook URL** button. Note this URL for the [**Discord Webhook URL** setting](discord-webhook-custom-function.md#discord-webhook-url) in MindStudio’s Discord Webhook Custom Function.

## Configuration

### Discord Webhook URL

Enter the URL for your Discord channel’s webhook.

### Input

Enter the text to send to the Discord channel’s webhook. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the text. **Example**

```
{{Input}}
```
