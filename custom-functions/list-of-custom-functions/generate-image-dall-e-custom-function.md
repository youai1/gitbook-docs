---
description: >-
  Build a MindStudio AI that asks the app user for a description of an image,
  and then automatically generate that image.
---

# Generate Image (Dall-E): Custom Function

## What is Dall-E?

[Dall-E](https://openai.com/dall-e-3) is OpenAI’s text-to-image generator. Dall-E-3 is the latest iteration of this image generator.

## What Can I Do With MindStudio and Dall-E?

Build a MindStudio AI that asks the app user for a description of an image, and then automatically generate that image.

## What is Required for This Custom Function?

* OpenAI account.
* OpenAI API Key. See [Get OpenAI API Key](generate-image-dall-e-custom-function.md#get-openai-api-key).
* **Generate Image (Dall-E)** Custom Function.

## Get OpenAI API Key

1. Login to your OpenAI account.
2. Navigate to **API Keys**.
3. Select **Create new secret key**.
4. Store the API key for the [**OpenAI API Key** setting](generate-image-dall-e-custom-function.md#openai-api-key) in MindStudio’s Dall-E Custom Function. Do not close the browser window until doing so.

## Configuration

### OpenAI API Key

Enter your OpenAI API key.

### Model

Select which Dall-E model generates the image:

* Dall-E 3 (default option).
* Dall-E 2.

### Prompt

Enter the prompt that describes the image to generate. Optionally, reference a [Variable](https://docs.google.com/document/d/1lxI\_CFnecpT1euzJ0F3j6eg4tJCFtY9nNliRFr48POk/edit) that stores the prompt. **Example:**

```
{{Prompt}}
```

### Response Data Variable

Enter the Variable that stores GPT-4 Vision’s response. **Example:**

```
{{Response}}
```

### Output Variable

Enter the Variable in which to store the returned Dall-E image URL. Note to not use double curly braces when entering the Variable name into the Output Variable setting. **Example:**

```
Image
```
