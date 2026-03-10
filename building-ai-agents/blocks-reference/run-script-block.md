---
description: Execute a Workflow Script from the Automations Canvas.
---

# Run Script Block

## Overview

The **Run Script** block runs a Workflow Script file and maps its inputs and outputs to workflow variables. It acts as the connection point between a script written in the Script Editor and the broader workflow on the Automations Canvas.

See [Workflow Scripts](../workflow-scripts.md) to get started.

## Configuration

### Source Code

Select the Workflow Script file you want to run from the dropdown. Source code that will be executed when the Agent runs.

### Parameters

#### Input Variables

Map workflow variables to the script's input parameters. Each row shows the parameter name and the workflow variable to assign to it.

<table><thead><tr><th width="203.83203125">Field</th><th>Description</th></tr></thead><tbody><tr><td>Parameter name</td><td>The input parameter defined in the script (e.g., <code>topic</code>)</td></tr><tr><td>Variable</td><td>The workflow variable whose value will be passed in (e.g., <code>{{topic}}</code>)</td></tr></tbody></table>

{% hint style="info" %}
Assign values to the launch variables of the selected script.
{% endhint %}

#### Output Variables

Map the script's return values to workflow variables so they can be used by following blocks.

<table><thead><tr><th width="206.19921875">Field</th><th>Description</th></tr></thead><tbody><tr><td>Return key</td><td>The key from the script's return object (e.g., <code>summary</code>)</td></tr><tr><td>Variable</td><td>The workflow variable to store the value in (e.g., <code>{{summary}}</code>)</td></tr></tbody></table>

{% hint style="info" %}
Map the return values of the script to workflow variables.
{% endhint %}
