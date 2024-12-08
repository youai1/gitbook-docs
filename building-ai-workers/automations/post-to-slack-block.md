---
description: Send messages from your AI Worker directly to a Slack channel
---

# Post to Slack Block

The **Post to Slack Block** allows you to send messages directly to a Slack channel as part of your workflow. This block is perfect for automating updates, team notifications, or alerts with customizable formatting.

## **Configurations**

### **Message Type**

Choose how the message will be formatted before sending to Slack:

* **Markdown Text**: Use Slack-compatible Markdown to create formatted text messages \
  (e.g., **`bold*`**, **`_italic_`**, **`>`** for blockquotes).
* **Slack Block Kit Blocks**: Design a highly customized message layout using Slack's **Block Kit**. Block Kit enables advanced formatting, such as interactive elements, sections, dividers, and more. Learn more at [Slack Block Kit Documentation](https://api.slack.com/block-kit).

### **Channel**

Connect to a Slack channel where the message will be posted.

* Click **Add to Slack** to authenticate and link your Slack account.
* Once connected, select the desired channel from your Slack workspace.

#### **Message Content**

Compose your message in markdown or build your custom Slack block.

***

## How to Write Slack Blocks

Slack blocks are modular and interactive components used to create rich, visually engaging messages in Slack. With the [Slack Block Kit](https://api.slack.com/block-kit), you can stack and arrange blocks to design powerful message layouts that deliver information or enable user interactions.

### **Block Basics**

Blocks are the building units for creating structured, visually appealing Slack messages. They are stackable components designed to display text, images, buttons, and other elements in a flexible, layout-friendly way.

### **Types of Blocks**

Blocks are the core components used to structure and organize the content of your Slack messages.

<table><thead><tr><th width="181">Block Type</th><th>Description</th></tr></thead><tbody><tr><td><strong>Actions</strong></td><td>Contains interactive elements like buttons and menus.</td></tr><tr><td><strong>Context</strong></td><td>Displays small contextual information with images or text.</td></tr><tr><td><strong>Divider</strong></td><td>Adds a horizontal line to separate content.</td></tr><tr><td><strong>File</strong></td><td>Displays information about remote files.</td></tr><tr><td><strong>Header</strong></td><td>Displays large, bold text for headings.</td></tr><tr><td><strong>Image</strong></td><td>Displays standalone images.</td></tr><tr><td><strong>Input</strong></td><td>Collects user input via various input types.</td></tr><tr><td><strong>Rich Text</strong></td><td>Allows formatted and structured text.</td></tr><tr><td><strong>Section</strong></td><td>Displays text alongside optional block elements like buttons or images.</td></tr><tr><td><strong>Video</strong></td><td>Embeds a video player.</td></tr></tbody></table>

### **Block Elements**

Block elements are the interactive or visual components embedded inside blocks to enrich the functionality of your message.

<table><thead><tr><th width="212">Element Type</th><th>Description</th></tr></thead><tbody><tr><td><strong>Button</strong></td><td>Provides users with a direct path to performing actions like confirming tasks.</td></tr><tr><td><strong>Checkboxes</strong></td><td>Allows users to select multiple options from a list.</td></tr><tr><td><strong>Date/Time Pickers</strong></td><td>Enables users to select a date, time, or both.</td></tr><tr><td><strong>Dropdown Menus</strong></td><td>Lets users choose from a list of options.</td></tr><tr><td><strong>Plain Text Input</strong></td><td>Allows users to enter freeform text.</td></tr><tr><td><strong>Radio Buttons</strong></td><td>Limits users to selecting one option.</td></tr><tr><td><strong>Image</strong></td><td>Displays an image as part of a larger block of content.</td></tr><tr><td><strong>Overflow Menu</strong></td><td>Provides a button that shows a list of additional options.</td></tr><tr><td><strong>Multi-Select Menu</strong></td><td>Lets users select multiple options from a dropdown list.</td></tr></tbody></table>

### **Composition Objects**

Composition objects allow you to enhance the structure of blocks and elements, enabling even more customization and interactivity.

<table><thead><tr><th width="257">Composition Object</th><th>Description</th></tr></thead><tbody><tr><td><strong>Confirmation Dialog Object</strong></td><td>Adds a confirmation step to interactive elements like buttons.</td></tr><tr><td><strong>Conversations Filter Object</strong></td><td>Filters the list of options in conversation selector menus.</td></tr><tr><td><strong>Option Object</strong></td><td>Represents a single item in a list of options for selection elements.</td></tr><tr><td><strong>Option Group Object</strong></td><td>Groups options in select menus for better organization.</td></tr><tr><td><strong>Text Object</strong></td><td>Defines text formatting for different blocks and elements.</td></tr><tr><td><strong>Workflow Object</strong></td><td>Contains workflow trigger information for running specific workflows.</td></tr><tr><td><strong>Slack File Object</strong></td><td>Represents a file for use in <strong>Image</strong> or <strong>File</strong> blocks.</td></tr></tbody></table>

***

### **Design Slack Blocks Using Slack's Block Kit Builder**

Slack’s [Block Kit Builder](https://app.slack.com/block-kit-builder/) lets you visually design your blocks, test layouts, and prototype quickly. It provides:

* Drag-and-drop elements to stack and organize blocks.
* Previews to refine your design.
* Click **Copy Payload** button to copy and paste JSON into your app.

### **Slack Block Kit Reference Examples**

#### **Example 1: Simple Task Update**

```json
{
  "blocks": [
    {
      "type": "header",
      "text": {
        "type": "plain_text",
        "text": "Task Update"
      }
    },
    {
      "type": "section",
      "text": {
        "type": "mrkdwn",
        "text": "*Task Completed:* The task `{{taskName}}` is finished!"
      }
    },
    {
      "type": "divider"
    },
    {
      "type": "actions",
      "elements": [
        {
          "type": "button",
          "text": {
            "type": "plain_text",
            "text": "View Task"
          },
          "url": "{{taskLink}}"
        }
      ]
    }
  ]
}
```

#### **Example 2: Collecting User Feedback**

```json
{
  "blocks": [
    {
      "type": "section",
      "text": {
        "type": "mrkdwn",
        "text": "We’d love your feedback! How would you rate your experience?"
      }
    },
    {
      "type": "actions",
      "elements": [
        {
          "type": "radio_buttons",
          "options": [
            {
              "text": {
                "type": "plain_text",
                "text": "Excellent"
              },
              "value": "excellent"
            },
            {
              "text": {
                "type": "plain_text",
                "text": "Good"
              },
              "value": "good"
            },
            {
              "text": {
                "type": "plain_text",
                "text": "Needs Improvement"
              },
              "value": "needs_improvement"
            }
          ]
        }
      ]
    }
  ]
}
```
