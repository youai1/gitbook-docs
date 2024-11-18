---
description: Learn what is Variable does in MindStudio.
---

# What is a Variable?

A Variable stores a value that represents data passed through the AI model. Create and reference Variables throughout your [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md).

Reference Variables in messages sent to the AI model by using double curly braces around the Variable name. When the message is sent to the AI model, the contents stored by the Variable replace the Variable reference.

**Example:**

`{{VariableName}}`

New Variables are created and assigned when:

* A new [User Input](what-is-a-user-input.md) is created.
* An Automation Block saves its result/output.
