---
description: Manage the Workflows in your AI.
---

# Manage Workflows

## Overview

Your AI can use more than one Workflow. Each Workflow requires:

* a [Prompt](../prompt-writing/what-is-a-prompt.md)
* an [Automation Workflow](what-is-an-automation-workflow.md)
* [the underlying AI model](../model-settings/view-underlying-ai-model-settings.md) that Workflow sends and receives responses

Note that each [Send Message Block](types-of-automation-blocks/#send-message-block) in any Automation Workflow can use different AI models than the primary AI model.

Your AI requires at least one Workflow.

## Create a New Workflow

Select the (**+**) icon next to the Workflows folder.

The new Workflow displays in the **Workflows** folder. It is named **Workflow.flow** unless an existing Workflow has that root name. If this is the case, a number follows the root name.

## Edit a Workflow

1. Open the **Workflows** folder in the **Explorer** tab.
2. Select the Workflow to edit. The Automation Canvas opens.

## Duplicate a Workflow

1. Open the **Workflows** folder in the **Explorer** tab.
2. Right-click on the Workflow to duplicate.
3. Select the **Duplicate** option.

The duplicated Workflow displays in the **Workflow** folder using the root name of the original with a number following it.

## Set a Workflow as the Entry Workflow

There are two ways to set the Entry Workflow:

* Right-click on a Workflow in the folder and select the **Set as entry workflow** option from the drop-down menu.
* Navigate to [**Global Settings**](../ai-app-settings/set-global-settings.md) and select your [Entry Workflow](../ai-app-settings/set-global-settings.md#entry-workflow) from the drop-down menu.

## Rename a Workflow

1. Open the **Workflow** folder in the **Explorer** tab.
2. Right-click on the Workflow to rename.
3. Select the **Rename** option. A form field appears.
4. Enter your new name for the Workflow.

## Delete a Workflow

1. Open the **Workflow** folder in the **Explorer** tab.
2. Right-click on the Workflow to delete.
3. Select the **Delete** option from the drop-down menu.
4. Confirm your deletion.

Ensure:

* your AI has one Workflow
* one has been set as the Entry Workflow
