---
description: Reference Variables in messages included in Send Message Blocks.
---

# Reference Variables in Message Processing

## Overview

If you use [Retrieval Augmented Generation (RAG)](../data-sources/query-a-data-source.md#retrieval-augmented-generation-rag) to query a [Data Source](../data-sources/what-is-a-data-source.md) before every AI output, you may include Variables inside of the Message Processing Template.

## Reference Variables in Custom Functions

Some [Custom Function](../custom-functions/what-is-a-custom-function.md) Blocks can reference a [Variable](what-is-a-variable.md) and assign a Variable within the same Block.

When you call a Variable, ensure you reference the Variable as shown in the Overview. When you assign the output Variable, curly braces are not needed.
