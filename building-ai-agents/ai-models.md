---
description: Learn about choosing the right AI models for the right task.
---

# AI Models

MindStudio provides access to over 50 AI models from leading providers, allowing you to tailor your workflows for a variety of tasks and use cases.

## **Select an Underlying AI Model**

The underlying model is the AI model that is inherited by the rest of the workflow. It’s configuration will be used as the default model for all blocks that use AI.

1. **Access Model Settings**
   * Navigate to the **Model Settings Tab** in your workflow editor.
2. **Choose an AI Model**
   * Click on the Model Card to view information about the AI Model.
   * **NOTE:** Some models may be locked and can be unlocked by adding a payment method in your Billing Settings.
3. Click the **Use Button** to confirm your selection
4. (Optional) Click the heart icon to add preferred AI Models to your Favorites section

***

## **Configuring Model Settings**

There are two configuration options for AI models:

1. **Temperature**
   * Controls the randomness of responses:
     * **Higher Temperature**: More creative, but less predictable.
     * **Lower Temperature**: More consistent, but less diverse.
2. **Max Response Size**
   * Defines the maximum size of the model’s response in tokens.
   * Example: 400 tokens ≈ 300 words.

### **Best Practices for AI Model Configuration**

* Start the slider in the center for temperature and adjust based on your needs.
* Use larger response sizes for detailed outputs and smaller sizes for concise ones.

***

## **Using Multiple AI Models Within a Workflow**

Every block that uses AI has the ability to override the underlying models settings and use its own unique AI model and configuration. This allows you to use different models in the workflow based on the task required at each specific step of the workflow.

***

## **Considerations When Selecting an AI Model**

Choosing the right AI model is critical to ensuring your workflow meets performance, cost, and quality requirements. MindStudio provides a variety of models with different capabilities, trade-offs, and configurations. When selecting a model, it's often necessary to balance these considerations to align with your workflow's goals and constraints.

### **Price**

AI models come with varying pricing structures based on usage, typically measured in tokens for prompt and response.

Use cost-effective models for high-volume, repetitive tasks (e.g., bulk summarization). Opt for premium models only when high output quality is critical.

### **Latency**

Latency refers to the time the model takes to generate a response. Low-latency models are essential for real-time or interactive workflows.

Prioritize low-latency models for use cases like chatbots or live applications. For non-time-sensitive workflows (e.g., scheduled reports), higher latency models with better quality may be acceptable.

### **Output Quality**

Different models vary in their ability to generate coherent, creative, or factual responses. Output quality depends on the model’s training and capabilities.

Choose advanced models for nuanced tasks like legal summaries or creative writing. Use simpler models for straightforward tasks like data extraction.

### **Context Window**

The context window determines the maximum amount of text the model can process at once. Larger context windows are essential for tasks involving lengthy inputs.

Use models with large context windows for summarizing lengthy documents or analyzing extensive datasets. For shorter inputs, a smaller context window may suffice and reduce costs.

## AI Models Reference

**Last updated:** May 5, 2025

### Amazon

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="150.16143798828125">Input Price</th><th width="150.25">Output Price</th><th width="160.1839599609375">Context Length</th><th width="150.15277099609375">Max Output Size</th></tr></thead><tbody><tr><td>Amazon Nova Lite</td><td>$0.06/MTok</td><td>$0.24/MTok</td><td>300,000 Tokens</td><td>5,000 Tokens</td></tr><tr><td>Amazon Nova Micro</td><td>$0.04/MTok</td><td>$0.14/MTok</td><td>128,000 Tokens</td><td>5,000 Tokens</td></tr><tr><td>Amazon Nova Pro</td><td>$0.80/MTok</td><td>$3.20/MTok</td><td>300,000 Tokens</td><td>5,000 Tokens</td></tr></tbody></table>

### Anthropic

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="149.57464599609375">Input Price</th><th width="149.8255615234375">Output Price</th><th width="160.1180419921875">Context Length</th><th width="149.58587646484375">Max Output Size</th></tr></thead><tbody><tr><td>Claude</td><td>$8.00/MTok</td><td>$24.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 2</td><td>$8.00/MTok</td><td>$24.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3 Haiku</td><td>$0.25/MTok</td><td>$1.25/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3 Haiku (Bedrock)</td><td>$0.25/MTok</td><td>$1.25/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3 Opus</td><td>$15.00/MTok</td><td>$75.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3 Opus (BedRock)</td><td>$15.00/MTok</td><td>$75.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3 Sonnet</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3 Sonnet (Bedrock)</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3.5 Haiku</td><td>$0.80/MTok</td><td>$4.00/MTok</td><td>200,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Claude 3.5 Haiku (Bedrock)</td><td>$0.80/MTok</td><td>$4.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3.5 Sonnet</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Claude 3.5 Sonnet (Bedrock)</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>Claude 3.5 Sonnet (20240620)</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Claude 3.5 Sonnet v2 (Bedrock)</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Claude 3.7 Sonnet</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>128,000 Tokens</td></tr><tr><td>Claude Instant</td><td>$0.80/MTok</td><td>$2.40/MTok</td><td>200,000 Tokens</td><td>4,096 Tokens</td></tr></tbody></table>

### Cohere

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="150.05291748046875">Input Price</th><th width="149.950439453125">Output Price</th><th width="159.6676025390625">Context Length</th><th width="150.17706298828125">Max Output Size</th></tr></thead><tbody><tr><td>Command</td><td>$1.50/MTok</td><td>$2.00/MTok</td><td>4,000 Tokens</td><td>4,000 Tokens</td></tr><tr><td>Command Light</td><td>$0.30/MTok</td><td>$0.60/MTok</td><td>4,000 Tokens</td><td>4,000 Tokens</td></tr><tr><td>Command R</td><td>$0.50/MTok</td><td>$1.50/MTok</td><td>128,000 Tokens</td><td>4,000 Tokens</td></tr><tr><td>Command R (Bedrock)</td><td>$0.15/MTok</td><td>$0.60/MTok</td><td>128,000 Tokens</td><td>4,000 Tokens</td></tr><tr><td>Command R+</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>128,000 Tokens</td><td>4,000 Tokens</td></tr><tr><td>Command R+</td><td>$2.50/MTok</td><td>$10.00/MTok</td><td>128,000 Tokens</td><td>4,000 Tokens</td></tr></tbody></table>

### DeepSeek

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="149.50604248046875">Input Price</th><th width="149.908935546875">Output Price</th><th width="160.0582275390625">Context Length</th><th width="149.71075439453125">Max Output Size</th></tr></thead><tbody><tr><td>DeepSeek-R1</td><td>$0.55/MTok</td><td>$2.19/MTok</td><td>64,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>DeepSeek-V3</td><td>$0.27/MTok</td><td>$1.10/MTok</td><td>64,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>DeepSeek-V3 (DeepInfra)</td><td>$0.40/MTok</td><td>$0.89/MTok</td><td>64,000 Tokens</td><td>8,000 Tokens</td></tr></tbody></table>

### Google

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="150.09637451171875">Input Price</th><th width="149.625">Output Price</th><th width="160.609375">Context Length</th><th width="150.21783447265625">Max Output Size</th></tr></thead><tbody><tr><td>Gemini 1.5 Flash</td><td>$0.04/MTok</td><td>$0.15/MTok</td><td>1,000,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Gemini 1.5 Pro</td><td>$0.63/MTok</td><td>$2.50/MTok</td><td>2,000,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Gemini 2.0 Flash</td><td>$0.15/MTok</td><td>$0.60/MTok</td><td>1,000,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Gemini 2.0 Flash-Lite</td><td>$0.07/MTok</td><td>$0.30/MTok</td><td>1,000,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Gemini 2.5 Flash</td><td>$0.15/MTok</td><td>$0.60/MTok</td><td>1,000,000 Tokens</td><td>65,536 Tokens</td></tr><tr><td>Gemini 2.5 Pro</td><td>$2.50/MTok</td><td>$15.00/MTok</td><td>1,000,000 Tokens</td><td>65,536 Tokens</td></tr><tr><td>Gemma 2 (Groq)</td><td>$0.20/MTok</td><td>$0.20/MTok</td><td>8,200 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Gemma 3.2 (DeepInfra)</td><td>$0.10/MTok</td><td>$0.20/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr></tbody></table>

### Meta

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="150.14410400390625">Input Price</th><th width="149.6207275390625">Output Price</th><th width="160.296875">Context Length</th><th width="150.06146240234375">Max Output Size</th></tr></thead><tbody><tr><td>Llama 3 70B (Groq)</td><td>$0.59/MTok</td><td>$0.79/MTok</td><td>8,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Llama 3 70B Instruct (DeepInfra)</td><td>$0.10/MTok</td><td>$0.10/MTok</td><td>8,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3 70B Instruct (Bedrock)</td><td>$0.10/MTok</td><td>$0.10/MTok</td><td>8,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3 8B (Groq)</td><td>$0.05/MTok</td><td>$0.08/MTok</td><td>8,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3 8B Instruct (DeepInfra)</td><td>$0.30/MTok</td><td>$0.60/MTok</td><td>8,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3 8B Instruct (Bedrock)</td><td>$0.30/MTok</td><td>$0.60/MTok</td><td>8,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 405B Instruct (DeepInfra)</td><td>$0.80/MTok</td><td>$0.80/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 405B Instruct (Bedrock)</td><td>$2.40/MTok</td><td>$2.40/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 70B Instruct (DeepInfra)</td><td>$0.23/MTok</td><td>$0.40/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 70B Instruct (Bedrock)</td><td>$0.72/MTok</td><td>$0.72/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 8B Instant (Groq)</td><td>$0.05/MTok</td><td>$0.08/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 8B Instruct (DeepInfra)</td><td>$0.03/MTok</td><td>$0.05/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.1 8B Instruct (Bedrock)</td><td>$0.22/MTok</td><td>$0.22/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.2 11B Instruct (Bedrock)</td><td>$0.16/MTok</td><td>$0.16/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.2 1B Instruct (Bedrock)</td><td>$0.10/MTok</td><td>$0.10/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.2 3B Instruct (Bedrock)</td><td>$0.15/MTok</td><td>$0.15/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.2 90B Instruct (Bedrock)</td><td>$0.72/MTok</td><td>$0.72/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 3.3 70B Versatile (Groq)</td><td>$0.59/MTok</td><td>$0.79/MTok</td><td>128,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>Llama 4 Maverick (DeepInfra)</td><td>$0.20/MTok</td><td>$0.60/MTok</td><td>130,000 Tokens</td><td>60,000 Tokens</td></tr><tr><td>Llama 4 Scout (Groq)</td><td>$0.11/MTok</td><td>$0.34/MTok</td><td>130,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Llama 4 Scout (DeepInfra)</td><td>$0.10/MTok</td><td>$0.30/MTok</td><td>130,000 Tokens</td><td>60,000 Tokens</td></tr></tbody></table>

### Mistral

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="150.00518798828125">Input Price</th><th width="150.2890625">Output Price</th><th width="160.2362060546875">Context Length</th><th width="150.45660400390625">Max Output Size</th></tr></thead><tbody><tr><td>Mistral 7B Instruct (DeepInfra)</td><td>$0.03/MTok</td><td>$0.06/MTok</td><td>4,100 Tokens</td><td>2,500 Tokens</td></tr><tr><td>Mistral 7B Instruct (Bedrock)</td><td>$0.15/MTok</td><td>$0.20/MTok</td><td>4,100 Tokens</td><td>2,500 Tokens</td></tr><tr><td>Mistral Codestral</td><td>$0.20/MTok</td><td>$0.60/MTok</td><td>32,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mistral Codestral Mamba</td><td>$2.50/MTok</td><td>$2.50/MTok</td><td>128,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mistral Large 2</td><td>$2.00/MTok</td><td>$6.00/MTok</td><td>128,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mistral Large 24.02 (Bedrock)</td><td>$4.00/MTok</td><td>$12.00/MTok</td><td>128,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mistral Large 24.07 (Bedrock)</td><td>$2.00/MTok</td><td>$6.00/MTok</td><td>128,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mistral Nemo</td><td>$0.15/MTok</td><td>$0.15/MTok</td><td>128,000 Tokens</td><td>64,000 Tokens</td></tr><tr><td>Mistral Small 24.02 (Bedrock)</td><td>$1.00/MTok</td><td>$3.00/MTok</td><td>128,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mistral Small 3.1 (25.03)</td><td>$0.10/MTok</td><td>$0.30/MTok</td><td>128,000 Tokens</td><td>16,000 Tokens</td></tr><tr><td>Mixtral 8x7B Instruct</td><td>$0.45/MTok</td><td>$0.70/MTok</td><td>4,100 Tokens</td><td>2,500 Tokens</td></tr></tbody></table>

### OpenAI

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="150.3046875">Input Price</th><th width="150.3585205078125">Output Price</th><th width="159.5113525390625">Context Length</th><th width="150.0615234375">Max Output Size</th></tr></thead><tbody><tr><td>GPT-4</td><td>$30.00/MTok</td><td>$60.00/MTok</td><td>8,200 Tokens</td><td>5,000 Tokens</td></tr><tr><td>GPT-4 Turbo</td><td>$10.00/MTok</td><td>$30.00/MTok</td><td>128,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>GPT-4.1</td><td>$2.00/MTok</td><td>$8.00/MTok</td><td>200,000 Tokens</td><td>100,000 Tokens</td></tr><tr><td>GPT-4.1 Mini</td><td>$0.40/MTok</td><td>$1.60/MTok</td><td>1,000,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>GPT-4.1 Nano</td><td>$0.10/MTok</td><td>$0.40/MTok</td><td>1,000,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>GPT-4.5</td><td>$75.00/MTok</td><td>$150.00/MTok</td><td>128,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>GPT-4o</td><td>$2.50/MTok</td><td>$10.00/MTok</td><td>128,000 Tokens</td><td>4,096 Tokens</td></tr><tr><td>GPT-4o Mini</td><td>$0.15/MTok</td><td>$0.60/MTok</td><td>128,000 Tokens</td><td>16,383 Tokens</td></tr><tr><td>o1</td><td>$15.00/MTok</td><td>$60.00/MTok</td><td>200,000 Tokens</td><td>100,000 Tokens</td></tr><tr><td>o1-mini</td><td>$3.00/MTok</td><td>$12.00/MTok</td><td>128,000 Tokens</td><td>65,536 Tokens</td></tr><tr><td>o1-pro</td><td>$150.00/MTok</td><td>$600.00/MTok</td><td>200,000 Tokens</td><td>100,000 Tokens</td></tr><tr><td>o3</td><td>$10.00/MTok</td><td>$40.00/MTok</td><td>200,000 Tokens</td><td>100,000 Tokens</td></tr><tr><td>o3-mini</td><td>$1.10/MTok</td><td>$4.40/MTok</td><td>200,000 Tokens</td><td>100,000 Tokens</td></tr><tr><td>o4-mini</td><td>$1.10/MTok</td><td>$4.40/MTok</td><td>200,000 Tokens</td><td>100,000 Tokens</td></tr></tbody></table>

### Perplexity

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="149.61456298828125">Input Price</th><th width="150.095458984375">Output Price</th><th width="159.8323974609375">Context Length</th><th width="150.32305908203125">Max Output Size</th></tr></thead><tbody><tr><td>Sonar</td><td>$1.00/MTok</td><td>$1.00/MTok</td><td>127,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>Sonar Deep Research</td><td>$2.00/MTok</td><td>$8.00/MTok</td><td>127,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Sonar Large Chat</td><td>$1.00/MTok</td><td>$1.00/MTok</td><td>127,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>Sonar Large Online</td><td>$1.00/MTok</td><td>$1.00/MTok</td><td>127,000 Tokens</td><td>28,000 Tokens</td></tr><tr><td>Sonar Pro</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>200,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Sonar Reasoning</td><td>$1.00/MTok</td><td>$5.00/MTok</td><td>127,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>Sonar Reasoning Pro</td><td>$2.00/MTok</td><td>$8.00/MTok</td><td>127,000 Tokens</td><td>8,000 Tokens</td></tr><tr><td>Sonar Small Chat</td><td>$0.20/MTok</td><td>$0.20/MTok</td><td>127,000 Tokens</td><td>32,768 Tokens</td></tr><tr><td>Sonar Small Online</td><td>$0.20/MTok</td><td>$0.20/MTok</td><td>127,000 Tokens</td><td>28,000 Tokens</td></tr></tbody></table>

### Reka

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="149.51910400390625">Input Price</th><th width="150.3038330078125">Output Price</th><th width="160.240478515625">Context Length</th><th width="150.35064697265625">Max Output Size</th></tr></thead><tbody><tr><td>Reka Core</td><td>$2.00/MTok</td><td>$2.00/MTok</td><td>128,000 Tokens</td><td>128,000 Tokens</td></tr><tr><td>Reka Edge</td><td>$0.10/MTok</td><td>$0.10/MTok</td><td>128,000 Tokens</td><td>128,000 Tokens</td></tr><tr><td>Reka Flash</td><td>$0.20/MTok</td><td>$0.80/MTok</td><td>128,000 Tokens</td><td>128,000 Tokens</td></tr></tbody></table>

### X.ai

<table data-full-width="true"><thead><tr><th>Model Name</th><th width="149.61895751953125">Input Price</th><th width="150.0738525390625">Output Price</th><th width="160.2535400390625">Context Length</th><th width="150.27496337890625">Max Output Size</th></tr></thead><tbody><tr><td>Grok 3</td><td>$3.00/MTok</td><td>$15.00/MTok</td><td>131,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Grok 3 Fast</td><td>$5.00/MTok</td><td>$25.00/MTok</td><td>131,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Grok 3 Mini</td><td>$0.30/MTok</td><td>$0.50/MTok</td><td>131,000 Tokens</td><td>8,192 Tokens</td></tr><tr><td>Grok 3 Mini Fast</td><td>$0.60/MTok</td><td>$4.00/MTok</td><td>131,000 Tokens</td><td>8,192 Tokens</td></tr></tbody></table>

### Image Models

<table data-full-width="true"><thead><tr><th>Provider</th><th>Model Name</th><th>Price</th><th>Prompt Length</th></tr></thead><tbody><tr><td>Amazon</td><td>Amazon Nova Canvas</td><td>$0.08 / image</td><td>1,000 Tokens</td></tr><tr><td>Black Forest Labs</td><td>FLUX 1.1 [pro]</td><td>$0.06 / image</td><td>10,000 Tokens</td></tr><tr><td>Black Forest Labs</td><td>FLUX 1.1 [pro] Ultra</td><td>$0.06 / image</td><td>10,000 Tokens</td></tr><tr><td>Ideogram</td><td>Ideogram Upscale</td><td>$0.06 / image</td><td>10,000 Tokens</td></tr><tr><td>Ideogram</td><td>Ideogram V1</td><td>$0.06 / image</td><td>10,000 Tokens</td></tr><tr><td>Ideogram</td><td>Ideogram V1 Remix</td><td>$0.06 / image</td><td>10,000 Tokens</td></tr><tr><td>Ideogram</td><td>Ideogram V2</td><td>$0.08 / image</td><td>10,000 Tokens</td></tr><tr><td>Ideogram</td><td>Ideogram V2 Remix</td><td>$0.08 / image</td><td>10,000 Tokens</td></tr><tr><td>Luma Labs</td><td>Photon 1</td><td>$0.02 / image</td><td>1,000 Tokens</td></tr><tr><td>Luma Labs</td><td>Photon 1 Flash</td><td>$0.00 / image</td><td>1,000 Tokens</td></tr><tr><td>OpenAI</td><td>DALL-E 2</td><td>$0.02 / image</td><td>1,000 Tokens</td></tr><tr><td>OpenAI</td><td>DALL-E 3</td><td>$0.08 / image</td><td>4,000 Tokens</td></tr><tr><td>OpenAI</td><td>GPT Image 1</td><td>$0.00 / image</td><td>4,000 Tokens</td></tr><tr><td>Stability</td><td>Stable Diffusion 3</td><td>$0.08 / image</td><td>10,000 Tokens</td></tr><tr><td>Stability</td><td>Stable Diffusion 3</td><td>$0.08 / image</td><td>10,000 Tokens</td></tr><tr><td>Stability</td><td>Stable Image Core</td><td>$0.04 / image</td><td>10,000 Tokens</td></tr><tr><td>Stability</td><td>Stable Image Core</td><td>$0.04 / image</td><td>10,000 Tokens</td></tr><tr><td>Stability</td><td>Stable Image Ultra</td><td>$0.08 / image</td><td>10,000 Tokens</td></tr><tr><td>Stability</td><td>Stable Image Ultra</td><td>$0.14 / image</td><td>10,000 Tokens</td></tr><tr><td>X.ai</td><td>Grok 2</td><td>$0.07 / image</td><td>131,000 Tokens</td></tr></tbody></table>

### Text-To-Speech Models

<table data-full-width="true"><thead><tr><th>Provider</th><th>Model Name</th><th>Input Price</th><th>Output Price</th><th>Prompt Length</th></tr></thead><tbody><tr><td>ElevenLabs</td><td>ElevenLabs TTS</td><td>$240.00 / 1M chars</td><td>$0.10 / 1M chars</td><td>Unlimited</td></tr><tr><td>OpenAI</td><td>GPT-4o-mini TTS</td><td>$0.60 / 1M chars</td><td>$2.40 / 1M chars</td><td>2,000 Characters</td></tr><tr><td>OpenAI</td><td>TTS</td><td>$15.00 / 1M chars</td><td>$0.10 / 1M chars</td><td>4,100 Characters</td></tr><tr><td>OpenAI</td><td>TTS HD</td><td>$30.00 / 1M chars</td><td>$0.10 / 1M chars</td><td>4,100 Characters</td></tr></tbody></table>

