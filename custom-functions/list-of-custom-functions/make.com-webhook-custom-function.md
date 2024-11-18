---
description: >-
  Build a MindStudio AI that processes data, then sends it to any of the dozens
  of services and applications that Make.com supports.
---

# Make.com Webhook: Custom Function

## What is Make.com?

[Make.com](https://www.make.com/en) provides a cloud-based automation platform to design, build, and automate workflows without the need for coding.

## What Can I Do With MindStudio and Make.com?

Build a MindStudio AI that processes data, then sends it to any of the dozens of services and applications that Make.com supports. In doing so, use a Make.com [webhook](https://www.webdatarocks.com/blog/webhooks-a-complete-guide-to-understanding/). For example, automatically Tweet about a blog post and then post that Tweet onto your social media content calendar on [Trello](https://trello.com/).

## What is Required for This Custom Function?

* Make.com account.
* Make.com [scenario](https://youtu.be/DmQ-C55oM34).
* Make.com webhook in that scenario. See [Create a Make.com Scenario with a Webhook](make.com-webhook-custom-function.md#create-a-make.com-scenario-with-a-webhook).
* **Make Webhook** Custom Function.

## Create a Make.com Scenario with a Webhook

1. Login to your Make.com account.
2. Click the **Create a new scenario** button.
3. Click the **+** button.
4. From the list of applications, select the **Webhooks** event.
5. Select the **Custom webhook** triggering event.
6. Select the **Add** button to create a new webhook.
7. Enter a webhook name into the **Webhook name** setting.
8. Click the **Save** button.
9. Click the **Copy to clipboard** button. Note this URL for the [**Make Webhook URL** setting](make.com-webhook-custom-function.md#make-webhook-url) in MindStudio’s Make Webhook Custom Function.
10. Click the **OK** button. The first module in the scenario is ready.
11. Add and configure the second module to which your MindStudio AI automatically sends data. For example, add the Trello application to the second module and configure its action to complete the scenario. When MindStudio triggers the webhook, the scenario sends that data to the second module, and then that application’s action runs.
12. Save the Make.com scenario.
13. Ensure to test the webhook in your MindStudio AI.
14. Ensure to start your scenario after testing.

## Configuration

### Make Webhook URL

Enter the URL for your Make scenario’s webhook.

### Input

Enter the text to send the Make.com scenario’s webhook. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the text. **Example:**

```
{{WebhookText}}
```
