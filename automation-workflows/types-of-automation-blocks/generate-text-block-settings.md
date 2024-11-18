---
description: Configure these settings for the Send Message Block.
---

# Generate Text Block Settings

## Create the Message

Enter in the **Message** setting the message to sent to the AI model to generate a text response. Reference [Variables](../../user-inputs-and-variables/what-is-a-variable.md) in messages sent to the AI model by using double curly braces around the Variable name. When the message is sent to the AI model, the contents stored by the Variable replace the Variable reference.

**Example:** `{{VariableName}}`

## Response Behavior

From the **Response Behavior** drop-down menu, select how to render the AI model’s response:

#### **Display to User** (default setting)

Display the AI model’s response to the app user.

From the Sender drop-down menu, select which agent sends the  message:

* **User:** The app sends the synthetic message on behalf of the user. The contents of the message are sent to the AI model. The AI model’s response is displayed to the app user. This is the default setting.
* **System:** The app sends the synthetic message directly to the user to simulate the AI model’s response.

#### Assign to Variable

The AI model’s response is assigned to a Variable.

In the **Variable Name** setting, enter the Variable name to assign the AI model’s response.

## Model Settings

MindStudio allows you to process messages in the Generate Text block with any available LLM. Your underlying model will be selected by default.&#x20;

<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Generate Text 1.png" alt=""><figcaption></figcaption></figure>

</div>
