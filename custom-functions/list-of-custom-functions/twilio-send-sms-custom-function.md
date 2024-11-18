---
description: >-
  Build a MindStudio AI that automatically sends text messages that AI creates
  for you.
---

# Twilio - Send SMS: Custom Function

## What is Twilio?

[Twilio](https://www.twilio.com/en-us) is a cloud-based platform that provides programmable communication tools using its web service APIs.

## What Can I Do With MindStudio and Twilio?

Build a MindStudio AI that automatically sends text messages that AI creates for you. Ask the app user:

* what to text to the target audience, such as a marketing promotion
* marketing style of the text message
* a link to learn more information about the promoted product or service
* the number for who sent the text message
* the recipient’s number to receive the text message

## What is Required for This Custom Function?

* Twilio account.
* Twilio string identifier (SID) for that account. See [Get Twilio Account SID](twilio-send-sms-custom-function.md#get-twilio-account-sid).
* Twilio auth token for that account. See [Get Twilio Auth Token](twilio-send-sms-custom-function.md#get-twilio-auth-token).
* **Twilio - Send SMS** Custom Function.

## Get Twilio Settings for This Custom Function

### Get Twilio Account SID

1. Navigate to your Twilio account.
2. Select the **Account** drop-down menu, and then select the **General settings** option.
3. In the **Verification code required for access** pop-up, enter the security code Twilio sends you to verify access to your account, and then select the **Verify** button.
4. Locate the **Account SID** setting. Note the SID for the [**Twilio Account SID** setting](twilio-send-sms-custom-function.md#twilio-account-sid) in MindStudio’s Twilio - Send SMS Custom Function.

### Get Twilio Auth Token

1. Return to the **General settings** option in your Twilio account.
2. Select the **API keys & tokens** link below the Twilio Account SID setting.
3. Locate the **Live credentials** section.
4. From the **Auth token** setting, copy the auth token. Note the auth token for the [**Twilio Auth Token** setting](twilio-send-sms-custom-function.md#twilio-auth-token) in MindStudio’s Twilio - Send SMS Custom Function.

## Configuration

### Twilio Account SID

Enter the SID for your Twilio account.

### Twilio Auth Token

Enter the text to send to the Discord channel. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the text. **Example:**

```
{{Input}}
```

### SMS Text

Enter the text for the text message. Optionally, reference a Variable that stores the text. **Example:**

```
{{Text}}
```

### FROM Number

Enter the sender’s number sending the text message. Optionally, reference a Variable that stores the sender’s number. **Example:**

```
{{SenderNumber}}
```

### TO Number

Enter the recipient’s number to receive the text message. Optionally, reference a Variable that stores the recipient’s number. **Example:**

```
{{RecipientNumber}}
```
