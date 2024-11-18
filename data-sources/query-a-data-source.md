---
description: >-
  Query a Data Source to leverage additional information beyond the AI model's
  default training data.
---

# Query a Data Source

## Overview

In order for the AI model to use the information in a [Data Source](what-is-a-data-source.md), set up your [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md) such that the AI queries that Data Source before sending responses to the user. There are two ways to query a Data Source.

## Query Data Automation Block

Query a Data Source by using a [Query Data Automation Block](../automation-workflows/types-of-automation-blocks/#query-data-source-block).

1. [Add a new Query Data Automation Block](../automation-workflows/add-a-block-to-an-automation-workflow.md).
2. Select the Data Source from the drop-down menu and assign a [Variable](../user-inputs-and-variables/what-is-a-variable.md) name for the query result.
3. Set the Max Results. See [Query Data Automation Block Settings](../automation-workflows/types-of-automation-blocks/query-data-block-settings.md).
4. Add your specific query to the Query Template.&#x20;

See [Reference a Data Source](reference-a-data-source.md) for more information.

## Retrieval Augmented Generation (RAG)

Query a Data Source before every AI response with Retrieval Augmented Generation RAG.

1. Select the [Terminator Block](../automation-workflows/types-of-automation-blocks/#terminator-block) in your Automation Workflow.
2. Under Message Processing, select Retrieval Augmented Generation (RAG) from the Strategy drop-down menu.
3. Select your Data Source from the drop-down menu.
4. Set the Max Result. See [Query Data Automation Block Settings](../automation-workflows/types-of-automation-blocks/query-data-block-settings.md).
