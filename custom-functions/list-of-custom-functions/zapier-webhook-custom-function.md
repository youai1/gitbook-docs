---
description: >-
  Build a MindStudio AI that automatically submits an email provided by the app
  user to your MailChimp subscriber list.
---

# Zapier Webhook: Custom Function

## What is Zapier?

[Zapier](https://zapier.com/) is a cloud-based platform that connects various apps and services to enable users to automate tasks.

## What Can I Do With MindStudio and Zapier?

Build a MindStudio AI that automatically submits an email provided by the app user to your MailChimp subscriber list.

## What is Required for This Custom Function?

* Zapier Premium account.
* Zap with a [webhook](https://www.webdatarocks.com/blog/webhooks-a-complete-guide-to-understanding/) to which to receive data. See [Get Webhook URL for Zap](zapier-webhook-custom-function.md#get-webhook-url-for-zap).
* **Zapier Webhook** Custom Function.

## Get Webhook URL for Zap

1. Select the ellipsis icon, and then select the **Create a new Zap** option.
2. Select the **1. Trigger** step that triggers your Zap.
3. Select the **Webhooks by Zapier** option.
4. From the **Event** drop-down menu, select the **Catch Hook** option.
5. Select the **Continue** button.
6. Do not select a Child Key. Click the **Continue** button.
7. From the **Your webhook URL** setting, select the **Copy** button. Note this URL for the [**Zapier Webhook URL** setting](zapier-webhook-custom-function.md#zapier-webhook-url) in MindStudio’s Zapier Webhook Custom Function.
8. Finish configuring the Zap with the action to perform when the webhook triggers. For example, configure the Zap’s action to connect to your MailChimp account and then add a subscriber.
9. Test the Zap to ensure the Zap’s webhook receives the MindStudio AI’s data.
10. Publish the Zap.

## Configuration

### Zapier Webhook URL

Enter the URL for your Zap’s webhook.

### Input

Enter the text to send to the Zap webhook. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the text. **Example:**

```
{{Input}}
```
