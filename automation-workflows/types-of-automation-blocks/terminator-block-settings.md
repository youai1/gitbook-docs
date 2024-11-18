---
description: Configure these settings for the Terminator Block.
---

# Terminator Block Settings

## Start Chat Session with App User

1. From the **Behavior** drop-down menu, select the **Chat** option.
2. Optionally, in the **System Introduction** setting in the **Chat Settings** section, enter the message to send the app user to start the chat session.
3. From the **Strategy** setting in the **Message Processing** section:
   1. Select the **No Processing** option to not process the chat session. This is the default option.
   2. Select the Retrieval Augmented Generation (RAG) option to allow the AI model to access a [Data Source](../../data-sources/what-is-a-data-source.md) to provide more up-to-date and specific information in their responses. See [Use Retrieval Augmented Generation (RAG)](terminator-block-settings.md#use-retrieval-augmented-generation-rag).

## Allow Files in a Data Source Be Made Viewable to the App User

1. From the **Behavior** drop-down menu, select the **Data Source Explorer** option.
2. Optionally, in the **System Introduction** setting in the **Chat Settings** section, enter the message to send the app user that the PDF(s) from a Data Source is available.
3. From the **Strategy** setting in the **Message Processing** section:
   1. Select the **No Processing** option to not process the chat session. This is the default option.
   2. Select the **Retrieval Augmented Generation (RAG)** option to allow the AI model to access a Data Source to provide more up-to-date and specific information in their responses. See [Use Retrieval Augmented Generation (RAG)](terminator-block-settings.md#use-retrieval-augmented-generation-rag).

## End the App Session

1. From the **Behavior** drop-down menu, select the **End Session** option.
2. Optionally, in the **System Introduction** setting in the **Chat Settings** section, enter the message to send the app user that the session has ended.
3. From the **Strategy** setting in the **Message Processing** section:
   1. Select the **No Processing** option to not process the chat session. This is the default option.
   2. Select the **Retrieval Augmented Generation (RAG)** option to allow the AI model to access a Data Source to provide more up-to-date and specific information in their responses. See [Use Retrieval Augmented Generation (RAG)](terminator-block-settings.md#use-retrieval-augmented-generation-rag).

## Use Retrieval Augmented Generation (RAG)

Retrieval Augmented Generation (RAG) allows the AI model to access a Data Source to provide more relevant and specific information in its responses.

1. From the **Data Source** setting, select which Data Source the AI model accesses during the chat session. If necessary, select the **New** button to [create a new Data Source](../../data-sources/create-a-data-source.md).
2. In the **Max Results** setting, enter the maximum number of results to save from the Data Source query. The maximum number of results is 5. The default is 1.
3.  In the **Template** setting, enter the message to send the AI model to provide it with the results from the Data Source query. The default message can be used as it is. You can customize it with different [Variables](../../user-inputs-and-variables/what-is-a-variable.md) to reference. Reference Variables by using double curly braces around the Variable name. When the message is sent to the AI model, the contents stored by the Variable replace the Variable reference.

    **Example:** `{{VariableName}}`
