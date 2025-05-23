---
description: Turn an entire AI agent into a re-useable automation block.
---

# Packaged Workflows

## Overview

Packaged Workflows turn an entire, multi-step agent into **one reusable drag-and-drop block**. Each block only exposes the inputs a builder needs (via a small form) and surfaces well-structured outputs, hiding all the looping, data-massaging, and citation logic inside the package.&#x20;

Packaged Workflows allow you to add sophisticated behavior to any agent in seconds, without rebuilding the same patterns over and over again.

## How to create a Packaged Workflow

Any MindStudio agent can become a package by setting the **Start Block Trigger** to **“Packaged Workflow.”**

<figure><img src="../.gitbook/assets/Trigger mode 1.png" alt=""><figcaption></figcaption></figure>

Once the trigger mode has been selected, follow the steps below to complete the configuration of the package.&#x20;

### Add the **package metadata**

1. **Category**: Select the block menu category where the package will be displayed.
2. **Status**: Select if the package is active, deprecated, or hidden.
3. **Transition type**
   1. **Dynamic**: The end block returns a key called <mark style="color:red;">`__transition`</mark> with the ID of the block to go to next. This setting should only be used in cases where there are multiple End blocks.&#x20;
      1.  **Example:** A logic block reviews data to determine if changes have been found.

          * **If changes are found** → finish at End block A (transition ID: X).
          * **If no changes are found** → finish at End block B (transition ID: Y).

          This lets the person using the block add separate transitions for “has changes” and “no changes."
   2. **Controlled**: The block only transitions to whatever the next block is in the sequence.&#x20;
4. **Name**: The display name for the package.
5. **Description**: A brief description of the package's functionality.
6. **Icon**: The icon image that will be displayed on the block menu.

### Define the **Input Schema**

These are the form fields the end user will see. The field options include:

* Text (or variable)
* Select dropdown (with options)
* Transition (lets the user select another block)

### **Expose Structured Outputs**&#x20;

Map internal variables to output names. These are the variables the block will expose downstream.&#x20;

<figure><img src="../.gitbook/assets/Frame 40.png" alt=""><figcaption></figcaption></figure>

### Add the Packaged Workflow to a Workspace

1. **Copy the agent ID** of the packaged workflow you want to share.
2. Open **Workspace Settings → Packaged Workflow Repositories**.
3. Paste the ID and click **Add**.
4. The new block appears instantly in the block picker for every builder in that workspace.&#x20;

In order to add the packaged workflow to the repository in your workspace, the packaged workflow must have [public use](publishing-and-versioning.md#public-use) turned on.

<figure><img src="../.gitbook/assets/Add repo.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Configuring a Start block as a packaged workflow turns it into its own standalone block. This lets you house several packaged workflows inside one agent instead of creating a separate agent for each, making your packages much easier to manage.
{% endhint %}

### The Standard Library (ready-made blocks)

Every workspace automatically includes the _**MindStudio Standard Library**_ of Packaged Workflows:

| Block                     | What it does                                                                                                                                |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Deep Research**         | Performs a Google-style deep search, gathers sources & citations, and returns a rich research bundle.                                       |
| **Generate Podcast**      | Writes a full podcast episode and records TTS audio.                                                                                        |
| **Track Website Changes** | Monitors a page and routes your flow based on whether the content has changed since the previous run (works great with scheduled triggers). |
| **Analyze CSV**           | Answers questions about a CSV by auto-writing and executing Python.                                                                         |
