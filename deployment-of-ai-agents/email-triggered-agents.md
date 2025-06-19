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

**The incoming email’s metadata and body are passed to the workflow via launch variables:**&#x20;

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
