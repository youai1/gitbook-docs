---
description: >-
  Learn about generating dynamic HTML with the Generate Asset block and agent
  loading screens.
---

# Dynamic HTML & Workflow Loading Styles

{% embed url="https://youtu.be/33IGwSEmaCE" %}

## What Is Dynamic HTML in MindStudio?

The **Generate Asset block** is one of the most powerful non-AI blocks in MindStudio. It allows you to create images, PDFs, and full HTML pages inside your agents.

Previously, you had to write HTML directly or carefully structure variables. With **Dynamic HTML**, you can now simply write a natural language prompt, and the AI will generate HTML for you.

Dynamic HTML is ideal for:

* Fast, creative webpage generation
* Styling AI outputs with minimal coding
* Prototyping custom layouts and visualizations
* Turning text outputs into engaging, shareable formats

***

## Enable Dynamic HTML

1. Open your **Generate Asset block**.
2. Under **Source Type**, choose **Dynamic HTML**.
3. Enter a natural language prompt describing your page layout and style.
   * Example: _“Use the poem, haiku, and image URL to create a modern, clean page. Trendy fonts, minimal design, artsy aesthetic.”_
4. Include variables directly (e.g., `{{poem}}`, `{{haiku}}`, `{{imageUrl}}`).

The model generates valid HTML automatically—no need to hand-code or manage data structures.

### Example: Build a Poem Page

**Workflow**

1. Generate a poem about a topic.
2. Generate a haiku on the same topic.
3. Create an image from the poem.
4. Pass these values (`poem`, `haiku`, `image URL`) into the Generate Asset block.
5. Prompt: _“Design a modern, clean web page to showcase the poems and image.”_

**Result**

* Custom image as header
* Poem and haiku placed in styled sections
* Page automatically rendered with your chosen style

***

## Workflow Loading Style

Instead of the default point cloud animation, you can now show users a **workflow preview** that reveals each step being executed.

This makes it easier to:

* Map agent activity to workflow steps
* Provide transparency into what’s running
* Create a more engaging user-facing experience

### Configure Loading Style

1. Open your agent’s **Metadata settings**.
2. Under **Runtime → Startup**, find **Loading Style**.
3. Choose:
   * **Point Cloud** (classic animation)
   * **Workflow Preview** (shows live execution steps)

{% hint style="info" %}
**Note:**&#x20;

* Newly created agents default to Workflow Preview.
* Existing agents keep their original loading style until changed.
{% endhint %}
