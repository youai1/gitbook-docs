---
description: >-
  Build a MindStudio AI that leverages GPT-4 Vision to automatically describe
  what is in an image.
---

# OpenAI GPT-4 Vision: Custom Function

## What is OpenAI GPT-4 Vision?

[OpenAI GPT-4 Vision](https://platform.openai.com/docs/guides/vision) (GPT-4V) integrates image processing into GPT-4 by accepting images and answering questions about them.

## What Can I Do With MindStudio and OpenAI GPT-4 Vision?

Build a MindStudio AI that leverages GPT-4 Vision to automatically describe what is in an image. With that text description, use another AI model to automatically generate ad copy for a marketing campaign.

For example, after receiving GPT-4 Vision’s response, use a [Send Message Block](../../automation-workflows/types-of-automation-blocks/#send-message-block) to message an AI model to generate three different ad copy ideas based on the GPT-4 Vision’s text description of the image.

## What is Required for This Custom Function?

* OpenAI account.
* OpenAI API Key. See [Get OpenAI API Key](openai-gpt-4-vision-custom-function.md#get-openai-api-key).
* GPT4-Vision Custom Function.

## Get OpenAI API Key

1. Login to your OpenAI account.
2. Navigate to **API Keys**.
3. Select **Create new API key**.
4. Store the API key for the [**OpenAI API Key** setting](openai-gpt-4-vision-custom-function.md#openai-api-key) in MindStudio’s GPT-4 Vision Custom Function. Do not close the browser window until doing so.

## Configuration

### OpenAI API Key

Enter your OpenAI API key.

### Image URL

Enter the image URL in which to generate marketing copy. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores:

* the image URL (from a [Short Text](../../user-inputs-and-variables/types-of-user-inputs/#short-text) User Input) or
* the uploaded image (from an [Upload Image](../../user-inputs-and-variables/types-of-user-inputs/#upload-image) User Input).

**Example:** `{{Image}}`

### GPT-4 Vision Instructions

Enter the instructions to send to GPT-4 Vision how to process the image. **Example:**

```
Describe what is in the following image:
```

Optionally, reference a Variable that stores the instructions the app user enters into a User Input. **Example:**

```
{{Instructions}}
```

### Response Data Variable

Enter the Variable that stores GPT-4 Vision’s response. **Example:**

```
{{Response}}
```

### Success Variable

Enter the Variable in which to store that GPT-4 Vision processed the image successfully. Note to not use double curly braces when entering the Variable name into the Success Variable setting. **Example:**

```
Success
```
