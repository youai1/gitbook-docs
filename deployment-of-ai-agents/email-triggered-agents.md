---
description: >-
  Trigger AI workflows by sending or forwarding emails to your Agent’s unique
  address — perfect for summaries, automation, and intelligent replies.
---

# Email-Triggered Agents

{% embed url="https://youtu.be/AkBR3ure1A8" %}

## Overview

Email-triggered AI Agents allow you to run workflows simply by forwarding or CC’ing an email thread to a special address tied to your Agent. These Agents are perfect for turning email content into structured, automated actions — without needing to open MindStudio directly.

#### Common use cases include:

* **Email Thread Summarization**: Get a digest of long email chains with action items and proposed replies.
* **Meeting Prep**: Summarize recent threads ahead of scheduled calls.
* **Follow-up Drafts**: Automatically generate a professional reply.
* **Document Intake**: Extract insights or metadata from attachments.
* **Support Triage**: Classify or escalate incoming messages.
* **CRM Logging**: Parse and forward important data to your system of record.
* **Content Generation**: Turn customer emails into tweets, summaries, or marketing copy.

## How It Works

When an AI Agent is set to use the **Email** run mode, MindStudio assigns it a unique, auto-generated email address. Any message sent to this address will automatically trigger the Agent.

<figure><img src="../.gitbook/assets/email trigger 1.png" alt=""><figcaption></figcaption></figure>

**The incoming email’s metadata and body are passed to the workflow via launch variables:**&#x20;

<figure><img src="../.gitbook/assets/email trigger 2.png" alt=""><figcaption></figcaption></figure>

* `from` – The sender’s email address
* `subject` – The subject line of the incoming email
* `message` – The full text content of the email
* `attachments` – Any files included in the email

After the workflow runs, the Agent can send an email response using the **Send Email** block — containing the output of the Agent.

## Key Features

* **Dedicated Trigger Address**: Every Agent gets its own email address.
* **Email Metadata Access**: Bring in data from the email.
* **Attachment Support**: Incoming files can be accessed as part of the workflow.
* **Sender Permissions**: Restrict usage to authorized email addresses.
* **Reply Automation**: Send structured responses directly to the inbox.
* **Automated Workflows**: Agents operate entirely from your inbox — no UI needed.

## Setup Requirements

To configure an AI Agent to trigger via email:

* Open the **Start Block** in your workflow.
* Set the **Run Mode** to `Email`.
* Use email-related launch variables.
* Use blocks like [**Generate Text**](../building-ai-agents/blocks-reference/generate-text-block.md) to analyze the message.
* Use [**Send Email**](../building-ai-agents/blocks-reference/send-email.md) to deliver a response.
* Copy your Agent’s trigger email address and forward messages to it.

***

## How to Setup Automatic Forwarding to an AI Agent in Gmail

{% embed url="https://www.loom.com/share/f529d1957837458c905bdb5dacf0cc15?sid=48f22fe6-c6ab-42fa-8bad-57a689d71526" %}

#### Step 1: Get Your Agent’s Trigger Email Address

1. Open your AI agent inside MindStudio.
2. Make sure the agent’s **Run Mode** is set to **Email**.
3. Copy the agent’s **trigger email address** — you’ll need this for Gmail.

***

#### Step 2: Add Forwarding Address in Gmail

1. Open Gmail and go to **⚙ Settings → See all settings**.
2. Navigate to the **Forwarding and POP/IMAP** tab.
3. Click **Add a forwarding address**.
4. Paste in the **trigger email address** from your agent.
5. Gmail will send a **confirmation email** to that address.

***

#### Step 3: Verify the Forwarding Address

1. In MindStudio, **publish your agent** so it can receive email.
2. In Gmail, click to resend the verification email.
3. The confirmation email will appear in the agent’s **debugger logs**.
4. Open the logs, find the confirmation link, and click it to verify.
5. Once confirmed, Gmail will accept that forwarding address.

***

#### Step 4: Create an Auto-Forwarding Filter

1. In Gmail, find an example of the email you want to forward (e.g., a newsletter).
2. Click the **three dots → Filter messages like this**.
3. In the filter settings, choose **Create filter**.
4. Select **Forward it to → \[your agent’s trigger email]**.
5. Confirm the action (you may need to verify again via your phone).
6. Save the filter.

***

#### Step 5: Test the Setup

* Send yourself a test email that matches the filter criteria.
* Check the agent’s debugger logs to confirm the email was forwarded and processed.
