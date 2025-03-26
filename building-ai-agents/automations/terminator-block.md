---
description: End the workflow with multiple end behaviors
---

# Terminator Block

The **Terminator Block** marks the endpoint of a workflow. It offers multiple behaviors to customize the user’s experience or finalize the workflow’s output. End behaviors define how workflow concludes, whether through interaction, document processing, or returning structured data.

## **Configurations**

Choose one of the following behaviors to define how the workflow ends:

### **Chat**

Provides a frontend native chat experience, ideal for conversational workflows.

#### **System Introduction (Optional)**:

An introductory message displayed at the start of the chat session. This is for display purposes only and is not included in the AI prompt.

#### **Message Processing Strategy**:

Choose how user inputs are processed before being sent to the AI. Options include no processing or custom strategies.

**No processing:** Does not pre-process the message in any way.

**Retrieval-Augmented Generation (RAG):** Incorporates external context from [Data Sources](../data-sources.md) into the AI’s responses. Enabling this strategy opens the following configurations:

* **Data Source**: Select or create a Data Source to provide the AI with additional context.
* **Max Results**: Set the maximum number of relevant results retrieved from the Data Source.
* **Template**: Define how retrieved context is combined with the user’s input.
  * <mark style="color:red;">`{{queryResult}}`</mark>: refers to the result of the Data Source query
  * <mark style="color:red;">`{{originalMessage}}`</mark>: refers to the message sent by the end user in the chat

#### **Other Settings**:

* **Model Mixer**: Allow users to use multiple LLM models during the chat. For example, a user can send a message and use model mixer to get a response from both Claude 3 Opus and GPT-4o.
* **Response Editing**: Enable users to edit LLM responses in the chat after a response has been returned.

***

### **Revise Document**

Leverages an AI-assisted Rich Text Editor to revise and enhance documents.

#### **Revision Template**:

Define the instructions for document revision.

* <mark style="color:red;">`{{selectedText}}`</mark>: refers to the highlighted text in the document editor.
* <mark style="color:red;">`{{instructions}}`</mark>: refers to the prompt entered when using AI-assisted revisions.

#### **System Introduction (Optional)**:

An introductory message displayed at the start of the chat session. This is for display purposes only and is not included in the AI prompt.

***

### **Data Source Explorer**

Enables users to chat with documents from a Data Source. Only works for PDF files.

#### **System Introduction (Optional)**:

An introductory message displayed at the start of the chat session. This is for display purposes only and is not included in the AI prompt.

***

### **End Session**

Finalizes the workflow and returns output values to the calling function or user.

#### **Return Data**:

* **JSON Output**: Define the final data to return using JSON format. Create key value pairs and use <mark style="color:red;">`{{variables}}`</mark> for [dynamic content](../variables.md).

#### **Notifications**:

* **Email**: Enable email notifications when the workflow ends.
  * When enabled, click on **+ Add** to enter the emails you’d like the notification sent to.
* **Slack**: Configure Slack notifications for workflow completion.
  * Click **Add to Slack** to authenticate and link your Slack account.
  * Once connected, select the desired channel from your Slack workspace you’d like the notification sent to.
