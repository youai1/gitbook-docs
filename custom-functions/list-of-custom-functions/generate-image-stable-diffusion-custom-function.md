---
description: >-
  Build a MindStudio AI that asks the app user for a description of an image,
  and then automatically generate that image.
---

# Generate Image (Stable Diffusion): Custom Function

## What is Stable Diffusion?

[Stable Diffusion](https://stability.ai/) is a text-to-image generator.

## What Can I Do With MindStudio and Stable Diffusion?

Build a MindStudio AI that asks the app user for a description of an image, and then automatically generate that image.

## What is Required for This Custom Function?

* Stable Diffusion account.
* Stable Diffusion API Key. See [Get Stable Diffusion API Key](generate-image-stable-diffusion-custom-function.md#get-stable-diffusion-api-key).
* **Generate Image (Stable Diffusion)** Custom Function.

## Get Stable Diffusion API Key

1. Login to your Stable Diffusion account.
2. Navigate to **API Keys**.
3. Select **Create API Key**.
4. Select the **Copy to Clipboard** icon.
5. Store the API key for the [**API Key** setting](generate-image-stable-diffusion-custom-function.md#api-key) in MindStudio’s Stable Diffusion Custom Function.

## Configuration

### API Key

Enter your Stable Diffusion API key.

### Prompt

Enter the prompt that describes the image to generate. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the prompt. **Example:**

```
{{Prompt}}
```

### Output Variable

Enter the Variable in which to store the returned Stable Diffusion image URL. Note to not use double curly braces when entering the Variable name into the Output Variable setting. **Example:**

```
Image
```
