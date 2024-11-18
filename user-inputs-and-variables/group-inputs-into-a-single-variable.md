# Group Inputs into a Single Variable

## Overview

You assign a [Variable](what-is-a-variable.md) name to each [User Input](what-is-a-user-input.md) that can be referenced in other parts of your [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md). To reference a group of User Inputs together without typing them individually, group those Variables into a single Variable name.

## Create An Input Folder

1. [Create a User Input](create-a-user-input.md).
2. In the **Variable** setting under the **General** section, enter the Variable name for this User Input that stores the group of other Variables.
3. Immediately after the Variable name, type an opening and closing bracket (`[]`). See [Example](group-inputs-into-a-single-variable.md#example).

The Input Folder displays in the User Inputs with your Variable name. [Add more User Inputs into the User Folder](group-inputs-into-a-single-variable.md#add-more-user-inputs-into-the-input-folder).

### Example

{% code overflow="wrap" %}
```
VariableName[]
```
{% endcode %}

## Add More User Inputs into the Input Folder

1. Create a new User Input to be grouped into the Input Folder.
2. In the **Variable** setting under the **General** section, enter the same Variable name used for the Input Folder, followed by an opening and closing bracket (`[]`).
3. Repeat these steps for each User Input to be grouped into the Input Folder.

Each grouped User Input displays within the Input Folder of that Variable name in the order that you created them.

You can change the Variable names within the Input Folder to no longer include a specific User Input within that group.
