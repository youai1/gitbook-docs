---
description: Learn the types of error events in MindStudio.
---

# Types of Errors and Warnings

## Overview

Events that will show up in the [**Errors** tab](view-the-errors-tab.md) include both errors and warnings. See the current list possible errors and warnings below.

## Errors

* [Data Source](../data-sources/what-is-a-data-source.md) contains invalid files. These files will be skipped on query.
* Data Source is empty. Queries will not return any results.
* Background [Send Message Block](../automation-workflows/types-of-automation-blocks/#send-message-block) does not define a [Variable](../user-inputs-and-variables/what-is-a-variable.md) to which to save its output.
* Message in a Send Message Block can not be empty.
* [Query Data Source Block](../automation-workflows/types-of-automation-blocks/#query-data-source-block) does not have a Data Source selected.
* Query Data Source Block is missing a query.
* Query Data Source Block does not define a Variable to which to save its output.
* [Run Function Block](../automation-workflows/types-of-automation-blocks/#run-function-block) does not specify a Function to execute.
* The Document Revision Template does not include both the Variables `{{selectedText}}` and `{{instructions}}`. Therefore, the AI will not know how to revise the user's selection.
* "Data Source Explorer" was selected as the terminator in a [Terminator Block](../automation-workflows/types-of-automation-blocks/#terminator-block), but no Data Source was found containing a valid PDF file. Only PDFs are compatible with Data Source Explorer at this time.
* User Message Preprocessor does not have a valid Data Source selected.
* User Message Preprocessing Template does not include both the Variables `{{originalMessage}}` and `{{queryResult}}`.

## Warnings

* The Variable `{{${foundVariable}}}` is referenced but does not exist.
* The configured temperature `${temperature}` for `${model}` is unstable and may result in garbled text or gibberish.
* [User Input Block](../automation-workflows/types-of-automation-blocks/#user-input-block) does not contain any Input Prompts.
* No Terminator or [Jump Block](../automation-workflows/types-of-automation-blocks/#jump-block) found.
* Query Data Source Block does not include any Variables in its Query Template.
