---
description: Dynamically gather information from a user.
---

# User Context Block

The User Context block utilizes AI to generate a series of questions to the user based on certain parameters.&#x20;

## Configuration

### Prompt&#x20;

Define the additional data you want to collect from the user. Like the Generate Text block, the prompt serves as a message to the AI, directing it to produce a specific output. In this instance, that output is a set of interview-style questions designed to gather more context from the user.

{% hint style="info" %}
The prompt may include variables.
{% endhint %}

### Interview Depth

Specify the level of context gathered by the AI. This setting will inform how probing the questions are and how comprehensive the final report will be.&#x20;

Three options are provided:

1. Quick (default)
2. Medium&#x20;
3. Thorough

### Max Questions

Set the amount of questions to be asked. By default, the max amount of questions will be set to 5.

{% hint style="info" %}
If the maximum is reached, the workflow will cotinue regardless of whether or not the model thinks the interview is complete.
{% endhint %}

### Variable Name

Save the responses to a variable that can be used in other parts of the workflow. Example: `My_Var`

### Output Format

Select the output format for the response data:

1. Text (Default)
2. JSON
