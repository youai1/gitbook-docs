---
description: Build a MindStudio AI that automatically sends promotional emails.
---

# Mailgun Send Email: Custom Function

## What is Mailgun?

[Mailgun](https://www.mailgun.com/) is an all-in-one email delivery platform.

## What Can I Do With MindStudio and Mailgun?

Build a MindStudio AI that automatically sends promotional emails.

## What is Required for this Custom Function?

* Mailgun account.
* Mailgun Email Delivery API Key. See [Get Mailgun Email Delivery API Key](mailgun-send-email-custom-function.md#get-mailgun-email-delivery-api-key).&#x20;
* A verified sending domain connected to your Mailgun account. See [Get Sending Domain](mailgun-send-email-custom-function.md#get-sending-domain).
* **Mailgun - Send Email** Custom Function.

## Get Mailgun Settings for This Custom Function

### Get Mailgun Email Delivery API Key

1. Login to your Mailgun account.
2. Navigate to your account settings.
3. Select the **API Security** option.
4. Select the **Create API** key setting from the **Mailgun API keys** section.
5. In the **New Api key** pop-up, enter a description, and then select the **Create Key** button.
6. Copy the API key that generates.
7. Store the API key for the [**Mailgun API Key** setting](mailgun-send-email-custom-function.md#mailgun-api-key) in MindStudio’s Mailgun Send Email Custom Function.

### Get Sending Domain

1. Navigate to your account settings.
2. Navigate to the **Sending domains** tab.
3. Copy the sending domain.
4. Store the sending domain for the [**Mailgun Domain** setting](mailgun-send-email-custom-function.md#mailgun-domain) in MindStudio’s Mailgun Send Email Custom Function.

## Configuration

### Mailgun API Key

Enter your Mailgun API key.

### Mailgun Domain

Enter your verified sending domain connected to your Mailgun account.

### Sender Email

Enter the email address from which the email sends. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores that email address in a User Input provided by the user. **Example:** `{{Sender}}`

### Receiver Email

Enter the email address that the email sends. Optionally, reference a Variable that stores that email address that the app user enters into a User Input. **Example:** {`{Recipient}}`

### Subject

Enter the email subject. Optionally, reference a Variable that stores that email subject that the app user enters into a User Input. **Example:** `{{Subject}}`

### Text

Enter the body text of the email. Optionally, reference a Variable that stores the email body text that a [Send Message Block](../../automation-workflows/types-of-automation-blocks/#send-message-block) saved from an AI synthetic message. **Example:** `{{Email}}`

### Success Output Variable

Enter the Variable in which to store that Mailgun sent the email successfully. Note to not use double curly braces when entering the Variable name into the Success Output Variable setting. **Example:** `Success`
