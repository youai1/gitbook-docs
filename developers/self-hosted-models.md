---
description: Connect and manage self hosted models to your AI agents.
---

# Self Hosted Models

{% hint style="info" %}
This feature is only available with a custom Enterprise plan. Please [contact us](https://www.mindstudio.ai/contact-us) for more information.
{% endhint %}

## What Are Self-Hosted Models?

Self-hosted models let you run any OpenAI-API-compatible checkpoint on your own hardware (or cloud) and plug it directly into MindStudio. This is ideal if you:

* Are a hobbyist experimenting with cutting-edge open-source models (e.g., Llama 3.2).
* Work at an organization that needs private, fine-tuned, or on-premise models.&#x20;

***

## How to Connect a Self-Hosted Model in MindStudio

#### **Prepare Your Model Endpoint**

* Run your model locally or on a server in an OpenAI-compatible way (for example, serving Llama 3.2 via `ncro`).&#x20;

#### **Open the Self-Hosted Models Panel**

* In your MindStudio workspace, click **Self-Hosted Models** in the sidebar.&#x20;

#### **Add a New Model**

* Click **Add New Model**.
* **Name**: Enter a friendly label (e.g., “Llama 3.2”).
* **API Name**: Choose an identifier you’ll use in blocks.
* **API Endpoint URL**: Paste the URL where your model is served (e.g., `http://localhost:8000/v1`).
* Leave all other settings at their defaults and click **Save**.&#x20;

#### **Use Your Self-Hosted Model in an Agent**

1. Create or open an existing agent.
2. Add a **Generate Text** block (or any block that uses a model).
3. In the block’s settings, switch to the **Self-Hosted** category and select your model (“Llama 3.2”).
4. Enter your prompt (e.g., “What is your name?”) and run.
5. Watch MindStudio route the request to your endpoint and return the result in the chat.&#x20;

***

### Compatibility & Notes

* **Any API-compatible service** works—open-source forks, private enterprise models, or on-premise deployments.
* **No extra setup** in your prompts or blocks; MindStudio handles routing transparently.
* **Visible requests**: You can observe incoming requests in your model logs to verify connectivity.
