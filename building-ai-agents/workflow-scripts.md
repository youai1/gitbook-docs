---
description: >-
  Build a workflow by describing it in plain language — or by assembling actions
  in code.
---

# Workflow Scripts

## What Is a Workflow Script?

A **Workflow Script** is a TypeScript file that defines workflow logic in code. Instead of connecting blocks on the Automations Canvas, you describe what your workflow should do, and the built-in AI agent writes the script for you. You can also add actions manually using the **+ Add Action** button.

Once written, a Workflow Script is executed on the Automations Canvas using a [Run Script](blocks-reference/run-script-block.md) block, which connects your script to the rest of your workflow — passing in inputs and mapping outputs to variables just like any other block.

No API keys or developer setup are required. Workflow Scripts run entirely within MindStudio.

## When to Use a Workflow Script

Workflow Scripts are a great fit when you want to:

* Build a workflow quickly by describing it in plain language
* Express multi-step logic (conditionals, loops, data formatting) more naturally than with visual blocks
* Consolidate several actions into a single, self-contained script
* Iterate on a workflow by chatting with the AI agent in the Script Editor

Workflow Scripts and visual workflows can also be combined — a single Run Script block can sit alongside other blocks on the canvas.

Inputs to the Workflow Script are specified as launch variables, such as from a [User Input](blocks-reference/user-input-block.md) block. Outputs from the Workflow Script are specified as output variables for following blocks.

## Creating a Workflow Script

### Step 1: Add a New Workflow Script

1. In the **Explorer** panel on the left, locate the **Workflows** section.
2. Click the **+** button, and then **Workflow Script**.
3. A new script file (e.g., `index.ts`) will be created and opened in the **Script Editor**.

<figure><img src="../.gitbook/assets/Run Script 01 (1).png" alt=""><figcaption></figcaption></figure>

The Script Editor has three main areas:

* **Left panel — AI Agent chat:** Describe your workflow in plain language. The AI agent reads your description, writes the TypeScript code, and explains what it built. You can ask follow-up questions, request changes, or iterate from there.
* **Center panel — Script Editor:** The generated (or manually written) TypeScript code is displayed here.
* **Right panel — Actions & Summary:**
  * **Actions**: Lists every MindStudio action (block) in your code — for example, Search Google or Generate Text — along with the line number where it appears. This gives you a quick overview of what your script does.
  * **Summary**: A plain-language explanation of the script, auto-generated from the code.

### Step 2: Build Your Workflow Script

#### Building by Describing

The fastest way to create a Workflow Script is to describe what you want to build in the AI Agent chat panel.

**Example prompt:**

> "Generate a script that asks the user for a topic to do a Google Search about. Google does a search on the top 5 responses. A Generate Text block summarizes the responses according to the user's topic, then displays that summary to the user."

The AI agent will:

1. Write the complete TypeScript script.
2. Show you the code in the center panel.
3. Explain what it built and suggest ways to extend it.
4. Answer your follow-up questions.

You can continue chatting to refine the script at any time.

#### Building by Adding Actions Manually

1. Click **+ Add Action** at the bottom of the Script Editor.
2. The block/connector selection modal will appear — the same one used on the Automations Canvas.
3. Select the action (block) you want to add.
4. The corresponding code will be inserted into your script.

{% hint style="info" %}
In the Script Editor, **Actions** and **Blocks** refer to the same thing. "Action" is the term used within the Script Editor; these are the same blocks you would otherwise place on the Automations Canvas.
{% endhint %}

### Step 3: Use the Script in a Workflow

A Workflow Script runs on the Automations Canvas via a **Run Script** block. This is how inputs are passed into the script and outputs are made available to the rest of the workflow.

1. Open or create a workflow (`.flow` file) in the Explorer.
2. On the **Automations Canvas**, add a **Run Script** block where you want the script to execute.
3. In the block's configuration panel on the right, set:
   1. **Source Code**: Select your Workflow Script file from the dropdown.
   2. **Input Variables**: Map workflow variables to your script's input parameters. For example, map `{{topic}}` from a User Input block to the `topic` parameter.
   3. **Output Variables**: Map your script's return values to workflow variables. For example, map the `summary` return value to `{{summary}}`.
4. The output variables are now available to any following block on the canvas — for example, a **Display Content** block to show `{{summary}}` to the user.

{% hint style="info" %}
User input is handled through launch variables passed into the script — not by adding a User Input action inside the script itself. Add a **User Input** block before the **Run Script** block on the canvas, then map its output variable to the script's input parameter in the Run Script block's Input Variables configuration.
{% endhint %}

How this example connects to a workflow:

`Start → User Input (collects topic) → Run Script (runs this script, passes in {{topic}}, outputs {{summary}}) → Display Content (displays {{summary}}) → End`

<figure><img src="../.gitbook/assets/Run Script 02.png" alt=""><figcaption></figcaption></figure>
