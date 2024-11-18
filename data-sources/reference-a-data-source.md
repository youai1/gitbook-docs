---
description: Reference a Data Source from within your AI's Automation Workflow.
---

# Reference a Data Source

## Overview

Integrating a Data Source into your Workflow allows the AI to leverage additional information beyond its default training data. In order to utilize a Data Source effectively, reference the Data Source in areas of your [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md).&#x20;

## Reference with a Query Data Automation Block

Reference your Data Source by using a [Query Data Automation Block](../automation-workflows/types-of-automation-blocks/query-data-block-settings.md).

1. Add a [new Query Data Automation Block](../automation-workflows/add-a-block-to-an-automation-workflow.md).
2. [Query the Data Source](../automation-workflows/types-of-automation-blocks/query-data-block-settings.md). Specify a [Variable](../user-inputs-and-variables/what-is-a-variable.md) name.
3. Provide instructions on how the AI should query the Data Source.

Note that uploading a Data Source DOES NOT mean the AI now knows everything about your file. You must instruct the AI on how to query that file for the AI to use your Data Source properly.

### Send Message Automation

Now that you have saved your Query Data Block as a Variable, reference that Variable in a [Send Message Block](../automation-workflows/types-of-automation-blocks/#send-message-block).

1. Select the (**+**) icon between Blocks on the Automation Canvas, or right-click and select **Send Message**.
2. In the **Message** setting, enter your message.
