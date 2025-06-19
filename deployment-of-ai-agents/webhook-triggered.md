---
description: >-
  Trigger AI workflows by sending an HTTP request to a unique webhook URL —
  ideal for automation tools, third-party integrations, or event-based systems.
---

# Webhook-Triggered

## Overview

Webhook-triggered Agents allow you to initiate an AI workflow via a simple HTTP POST request to a dedicated MindStudio webhook URL. This is a powerful option for connecting MindStudio with other tools, platforms, and automation systems — no frontend or user input required.

This method is ideal for:

* **Zapier, Make, or N8N Integrations**: Run Agents when events occur in other tools.
* **Internal Automations**: Trigger workflows from internal scripts, bots, or microservices.
* **Web App Hooks**: Fire off AI logic when users perform certain actions in your product.
* **Data Pipeline Steps**: Pass structured data into an AI Agent mid-process.

## How It Works

When an Agent is configured with the **Webhook** run mode, MindStudio generates a unique webhook URL. Any system that can send an HTTP `POST` request can trigger the Agent.

The **only launch variable** for this mode is `webhookParams`, which must be a JSON object. Your workflow can then reference `{{webhookParams.key}}` to access individual values inside that payload.

For example, if your POST payload includes `{ "email": "user@example.com" }`, you can access it in your workflow as `{{webhookParams.email}}`.

## Key Features

* **Single Endpoint Simplicity**: One URL, one variable — clean and predictable.
* **Structured JSON Input**: Pass any number of fields via `webhookParams`.
* **Realtime Execution**: Fast responses for on-demand actions.
* **Platform Compatible**: Works seamlessly with any system that can send a POST request.
* **Secure by Design**: Webhook URL is unlisted and unique per Agent.
* **Full Access to Blocks**: Use inputs anywhere in the workflow, just like other variable types.

## Setup Requirements

To configure an AI Agent to run via webhook:

* Open the **Start Block** in your workflow.
* Set the **Run Mode** to `Webhook`.
* Ensure your workflow uses `{{webhookParams}}` to reference incoming data.
* Assign outputs to named variables (e.g., `summary`, `classification`).
* Publish your Agent.
* Copy the provided **Webhook URL** from the Trigger section.

To trigger the Agent:

```http
POST https://v1.mindstudio-api.com/dev/your-webhook-id
Content-Type: application/json

{
  "webhookParams": {
    "customerName": "Jane Doe",
    "question": "What is your return policy?"
  }
}
```

Example reference inside the workflow:

* `{{webhookParams.customerName}}` → “Jane Doe”
* `{{webhookParams.question}}` → “What is your return policy?”
