---
description: Automate image generation with Dream AI.
---

# Generate Image (Dream AI): Custom Function

## What is Dream AI?

[Dream AI](https://dream.ai/) is a cloud-based AI platform to generate images and art.

## What Can I Do With MindStudio and Dream AI?

Build a MindStudio AI that asks the app user:

* for an idea to generate an image
* the image style
* the prompt to generate that image

&#x20;Automatically generate the image.

## What is Required for This Custom Function?

* Dream AI account.
* Dream AI API Key. Create one here. Store the API key in the [**DreamAI API Key** setting](generate-image-dream-ai-custom-function.md#dreamai-api-key) in MindStudio’s Dream AI Custom Function. Do not close the browser window until doing so.
* AI model for your MindStudio AI that can display images. Claude 3 Haiku is a great choice.
* **Generate Image (Dream AI)** Custom Function.

## Configuration

### DreamAI API Key

Enter your Dream AI API key.

### Image Style

Enter the image style number that is between 1 and 21 for the creativity style. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the text. **Example:**

```
{{Style}}
```

### Prompt

Enter the prompt in which to generate the image. Optionally, reference a Variable that stores the prompt. **Example:**

```
{{Prompt}}
```

### Output Variable

Enter the Variable in which to store the returned Dream AI image URL. Note to not use double curly braces when entering the Variable name into the **Output Variable** setting. **Example:**

```
Image
```
