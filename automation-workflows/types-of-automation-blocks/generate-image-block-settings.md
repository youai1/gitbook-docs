---
description: Configure settings for the Generate Image block.
---

# Generate Image Block Settings

## Craft a Prompt

In the prompt section of the configuration, add in the prompt that will be used to generate an image. Reference [Variables](../../user-inputs-and-variables/what-is-a-variable.md) in the prompt by using double curly braces around the Variable name. When the prompt message is sent to the AI model, the contents stored by the Variable replace the Variable reference.

**Example:** `{{VariableName}}`

## Set a Variable name

In the Variable Name text field, assign a name for output of the block. The image that is generated will be stored within that variable and can be referenced in other parts of the workflow.&#x20;

## Select Image Model

Under Model Settings, select the image model you would like to use. Note that usage costs differ depending on the model that is chosen. MindStudio offer the following image models.

* [DALL-E 2](https://openai.com/index/dall-e-2/)
* [DALL-E 3](https://openai.com/index/dall-e-3/)

<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Generate Image Docs.png" alt=""><figcaption></figcaption></figure>

</div>
