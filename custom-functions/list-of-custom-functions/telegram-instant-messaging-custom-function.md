---
description: >-
  Build a MindStudio AI that generates and sends announcements and messages to
  your public Telegram group.
---

# Telegram Instant Messaging: Custom Function

## What is Telegram?

[Telegram](https://telegram.org/) provides cloud-based end-to-end messaging services.

## What Can I Do With MindStudio and Telegram?

Build a MindStudio AI that generates and sends announcements and messages to your public Telegram group.

## What is Required for This Custom Function?

* Telegram account.
* Telegram bot. See [Create a Telegram Bot](telegram-instant-messaging-custom-function.md#create-a-telegram-bot).
* A public Telegram group to which to send the generated MindStudio messages. See [Create a Telegram group](telegram-instant-messaging-custom-function.md#create-a-telegram-group).
* [Invite your Telegram bot into your public group](telegram-instant-messaging-custom-function.md#invite-your-telegram-bot-into-your-public-group).
* [Copy the name of the Telegram group’s URL](telegram-instant-messaging-custom-function.md#copy-the-name-of-the-telegram-groups-url).
* **Telegram: Send a Message** Custom Function.

## Get Telegram Settings for This Custom Function

### Create a Telegram Bot

1. Log in to Telegram.
2. Locate the BotFather.
3. Enter `/start`
4. From the Telegram menu, select `/newbot`
5. Follow instructions to set a name and username for your bot.
6. Copy the API key that your bot generates.
7. Store the API key for the [**Telegram Bot API Key** setting](telegram-instant-messaging-custom-function.md#telegram-bot-api-key) in MindStudio’s Telegram Instant Messaging Custom Function.

### Create a Telegram Group

1. Select the Telegram group.
2. Select the **Edit** icon that looks like a pencil.
3. Select the **Group Type** setting.
4. Select the **Public Group** setting.
5. Set a link for this group.
6. Store the group name link.

### Invite Your Telegram Bot into Your Public Group

1. Go back two pages to view the members of the Telegram group.
2. Invite your Telegram bot into the group.

### Copy the name of the Telegram group’s URL

1. Copy from the `@` symbol to the end of the URL.
2. Note this URL segment for the [**Telegram Channel** setting](telegram-instant-messaging-custom-function.md#telegram-channel) in MindStudio’s Telegram Instant Messaging Custom Function.

## Configuration

### Telegram Bot API Key

Enter your Telegram bot API key.

### Telegram Channel

Enter the name of the public Telegram group channel to which to send the MindStudio message.

### Message

Enter the message to send to the Telegram group. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores that message in a User Input provided by the user. **Example:**

```
{{Message}}
```
