---
description: Start a chat session with AI
---

# Chat Block

## Configuration&#x20;

### Chat Settings&#x20;

#### System Introduction

This will be the first message presented to the user at the start of the chat session. It is only for display and not included as part of the prompt.&#x20;

#### Conversation Starters

Create a predefined message to help the user start the conversation.

Select the **"Add" button**, and the conversation starter in the **value section**.&#x20;

### Continuation Settings

#### Transition Control

Select how the user will transition out of the chat session. Options include:

* **None:** The chat session marks the end of the workflow.
* **Next Button:** The chat session shows a next button to take the user to the next step in the workflow.
  * Add a **button label.**
  * Select the **destination block** to continue the workflow.
  * **History Variable:** Save the chat session to a variable.
  * **Last Message Variable:** Save the last message sent by the user to a variable.&#x20;
* **Dynamic Tool Use:** Define a set of possible tools and allow the AI model to decide when and where to transition.&#x20;
  * **History Variable:** Save the chat session to a variable.
  * **Last Message Variable:** Save the last message sent by the user to a variable.&#x20;
  * **Add Tool:** Provide a text prompt that explains the purpose of the tool and select the destination block to continue the workflow.

### Message Proccessing&#x20;

#### Strategy&#x20;

Select whether this block should use **no processing** or **Retrieval Augmented Generation (RAG).**

If RAG is selected, you must select and configure a data source.
