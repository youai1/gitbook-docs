---
description: >-
  Learn how to quickly connect self-hosted models to MindStudio for testing &
  hobbyists
---

# Self-Hosted AI Models (Quickstart Tutorial)

## Prerequisites

Before getting started, ensure you have the following installed on your machine:

* [Ollama](https://ollama.com/)
* [Ngrok (for macOS)](https://ngrok.com/downloads/mac-os?tab=download)

***

## Step-by-Step Instructions

#### **1. Start an Ngrok Tunnel**

Open a terminal window and run the following command to expose port `11434` to the internet:

```bash
ngrok http http://localhost:11434
```

> Copy the forwarding HTTPS URL Ngrok provides (e.g. `https://xxxx.ngrok.io`). You'll need this later.

***

#### **2. Pull and Serve the AI Model**

Open a second terminal window:

**a. Pull the `llama3.2` model:**

```bash
ollama pull llama3.2
```

**b. Serve the model with the proper environment variables:**

Replace the Ngrok URL below with your actual forwarding address from Step 1:

**On Mac / Linux:**

```bash
OLLAMA_HOST=0.0.0.0:11434 OLLAMA_ORIGINS="https://xxxx.ngrok.io/" ollama serve
```

**On Windows:**

First

```bash
$Env:OLLAMA_HOST   = "0.0.0.0:11434"
$Env:OLLAMA_ORIGINS = "https://xxxx.ngrok.io/" 
```

then

```
ollama serve
```

> This command makes your local Ollama instance accessible through the Ngrok tunnel.

***

#### **3. Add the Self-Hosted Model to MindStudio**

1. Go to [MindStudio Self-Hosted Models](https://app.mindstudio.ai/workspace/self-hosted-models)
2. Click **"Add Model"**
3. Use the following fields:
   * **API Name**: (Ex: `llama3.2` )
   * **Endpoint**: `https://xxxx.ngrok.io/v1` (replace `xxxx` with your actual Ngrok subdomain)

> Your self-hosted AI model is now ready to be used in any MindStudio AI Agent.

***

## Using the Model in an Agent

Once added, you can:

* Select your AI Model in the **Model Settings** tab when editing an AI Agent.
* Use it across workflows, prompts, and block-level overrides in your automation.
