---
description: Assign Variable Names to User Inputs.
---

# Assign Variable Names to User Inputs

## Overview

User Inputs store collected data in a [Variable](what-is-a-variable.md) to be used across your [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md). By assigning each User Input with a Variable name, you choose where and when the AI references the value of that Variable.&#x20;

## Assign a Variable Name in a User Input

Assign Variable names inside the User Input configuration screen. See [Create a User Input](create-a-user-input.md) for more information on locating the configuration screen.

1. Locate the **Variable** setting under the **General** section. By default, this setting is labeled “input”.
2. Replace the text with a name of your choosing. Ensure that the name is unique in this AI. The name auto-saves after it is typed into the setting.

## Reference a Variable Name

[Reference a Variable](reference-variables-in-message-processing.md) anywhere in your AI Workflow by placing the Variable name between double curly braces.

**Example:** `{{VariableName}}`

NOTE: Any capitalization, symbols, or spacing must be used when referencing your Variable.
