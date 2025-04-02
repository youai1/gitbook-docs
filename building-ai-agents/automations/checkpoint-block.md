---
description: Allow for user review of a specific step in the workflow.
---

# Checkpoint Block

## Overview

The Checkpoint Block displays a prompt to the user, allows them to revise variables, accept or reject certain steps in the workflow and route them accordingly.&#x20;

## Configurations

### Modes

1. **Alert:** Allows users to accept or reject a workflow step before moving forward.
2. **Revise Variable:** Allows users to accept or reject a workflow step and make revisions to variables (i.e. generated content) before moving forward.&#x20;

### Title & Description

This section includes the actual prompt that is being displayed to the user.

#### Example:

**Title:** `Review Assets`

**Description:** `Review your generated assets and and continue when you are ready to finalize them for download.`

### Approve

Create a custom label to approve the displayed prompt. If this section is left blank, the label will automatically display **"Approve"**.

Route the approve label to the desired block by selecting the **Select Destination** button and then the desired block destination.&#x20;

<figure><img src="../../.gitbook/assets/Group 34049.png" alt="" width="563"><figcaption></figcaption></figure>

### Reject

Create a custom lable to reject the displayed prompt. If this section is left blank, the label will automatically display **"Reject"**.

Route the reject label to the desired block by selecting the **Select Destination** button.&#x20;

<figure><img src="../../.gitbook/assets/Group 34050.png" alt="" width="563"><figcaption></figcaption></figure>

### Revise Variable Configuration

This configuration is only visible if the **Revise Variable** mode is selected.

#### **Target Variable**

The variable that will be presented to the user to be accepted or revised. Example: `{{My_Var}}`

#### **Variable Label**

The name of the variable that will be displayed to the user. Example: `My Variable`

#### Variable Type

These are the types of content that can be revised

1. **Text** : includes any text based content generated using the Generate Text block.
2. **HTML** : includes images and pdfs generated using the Generate Asset block.

#### Revise Guidance

In this section, provide any additional context you might want to provide to the AI to use when making revisions to the content.&#x20;

#### Model Settings

Select the AI model to be used when making revisions to any variables.







#### &#x20;
