---
description: >-
  Use AI workflows as serverless functions inside your own applications — pass
  in variables and get structured responses.
---

# Running Agents via API

{% embed url="https://youtu.be/w1IqvJoVDEE" %}

## Overview

MindStudio AI Agents can be executed programmatically using the MindStudio API, making it easy to embed intelligent workflows directly into your own products, services, or backend systems. These Agents operate like serverless AI functions — take inputs, run logic, and return structured results.

This makes them ideal for:

* **Spam Detection**: Analyze user-generated content before publishing.
* **Form Validation**: Apply AI to check tone, clarity, or relevance in submitted data.
* **Product Recommendations**: Return AI-curated suggestions based on user input.
* **Support Triage**: Classify tickets or route inquiries programmatically.
* **SEO Optimization**: Analyze or rewrite submitted content dynamically.
* **Lead Scoring**: Evaluate and enrich captured lead data using AI.
* **Custom Workflows**: Run any internal logic that benefits from nuanced AI decision-making.

## How It Works

Once published, a MindStudio Agent can be triggered via HTTPS using a simple `POST` request to the MindStudio API. You pass in launch variables (inputs) as JSON, and the Agent runs its internal workflow using those inputs. The response is a structured JSON object that includes your defined output(s).

**You can:**

* Authenticate using an API key
* Specify which workflow to run (optional if using the entry workflow)
* Pass launch variables into the Agent
* Receive clean key-value outputs for use in your app logic

## Key Features

* **Serverless AI Functions**: Deploy logic without hosting or infrastructure.
* **Structured Inputs & Outputs**: Use JSON to pass variables and receive results.
* **Multiple Workflows per Agent**: Trigger specific flows as needed.
* **Rapid Testing**: Use the MindStudio debugger to simulate API calls.
* **Log Visibility**: View past requests, outcomes, and cost in the dashboard.
* **Developer Ready**: Easily integrate into frontend or backend systems.

## Developer Reference Docs

{% content-ref url="../developers/api-reference.md" %}
[api-reference.md](../developers/api-reference.md)
{% endcontent-ref %}

{% content-ref url="../developers/npm-package.md" %}
[npm-package.md](../developers/npm-package.md)
{% endcontent-ref %}
