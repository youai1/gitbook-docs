---
description: Learn about choosing the right AI models for the right task.
---

# AI Models

{% embed url="https://youtu.be/fTq0GFGL-vk" %}

MindStudio provides access to over 90 AI models from leading providers, allowing you to tailor your workflows for a variety of tasks and use cases.

## **Select an Underlying AI Model**

The underlying model is the AI model that is inherited by the rest of the workflow. It’s configuration will be used as the default model for all blocks that use AI.

1. **Access Model Settings**
   * Navigate to the **Model Settings Tab** in your workflow editor.
2. **Choose an AI Model**
   * Click on the Model Card to view information about the AI Model.
   * **NOTE:** Some models may be locked and can be unlocked by adding a payment method in your Billing Settings.
3. Click the **Use Button** to confirm your selection
4. (Optional) Click the heart icon to add preferred AI Models to your Favorites section

<figure><img src="../.gitbook/assets/Model Selector.png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../.gitbook/assets/Model Settings.png" alt=""><figcaption></figcaption></figure>

### **Best Practices for AI Model Configuration**

* Start the slider in the center for temperature and adjust based on your needs.
* Use larger response sizes for detailed outputs and smaller sizes for concise ones.

***

## **Using Multiple AI Models Within a Workflow**

Every block that uses AI has the ability to override the underlying models settings and use its own unique AI model and configuration. This allows you to use different models in the workflow based on the task required at each specific step of the workflow.

<figure><img src="../.gitbook/assets/Multiple Models.png" alt=""><figcaption></figcaption></figure>

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

See [Usage Pricing Reference](../usage-pricing-reference.md#ai-models-reference).

### Image Models

See [Usage Pricing Reference](../usage-pricing-reference.md#image-models).

### Vision Models

See [Usage Pricing Reference](../usage-pricing-reference.md#vision-models).

### Video Models

See [Usage Pricing Reference](../usage-pricing-reference.md#video-models).

### Text-To-Speech Models

See [Usage Pricing Reference](../usage-pricing-reference.md#text-to-speech-models).

### Speech-To-Text Models

See [Usage Pricing Reference](../usage-pricing-reference.md#speech-to-text-models).
