---
description: Update the title in the user's history
---

# Set Run Title

The Set Run Title block updates the title that appears in the user's run history for a given Run. This makes it easier for users to identify and organize previous interactions, especially when agents are used repeatedly with different content or contexts.

***

## Configurations

### New Title

Define the custom title that should appear in the user’s session history. **You may include variables** such as `{{user_input}}`, `{{summary}}`, or any previously defined step output to personalize the title.

***

#### **Examples**

**Example 1: Personalized Summary**\
`Summary of conversation with {{user_name}}`

**Example 2: Workflow Context**\
`Invoice generated for {{client_company}} on {{current_date}}`

***

## How It Works

1. When the block is reached during execution, it updates the title of the current run session in the user’s history.
2. The new title will immediately be reflected in the Workspace or Extension history views.
3. If no variables are present, the block will use the static text as-is.
