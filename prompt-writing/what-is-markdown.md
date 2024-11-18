---
description: Write your Prompt using Markdown syntax.
---

# What is Markdown?

## Overview

Markdown is a lightweight markup language to add formatting and structure to your [Prompts](what-is-a-prompt.md). Markdown is easy to use.

* Markdown structures your prompt into modular sections. Write your Prompt in sections to better instruct the AI model.
* Structured Prompts are more legible for collaborators or those that remix your AI for their own apps.

## Headers to Structure Your Prompt

Use a hashtag symbol (`#`) to create a header. The header is a section in your Prompt. Anything you type below that header becomes part of that section.

<div data-full-width="true">

<figure><img src="../.gitbook/assets/Markdown Prompt #1 (1).gif" alt=""><figcaption><p>Add header in Prompt</p></figcaption></figure>

</div>

Optionally, create sub-headers using two or three hashtag symbols to organize your Prompt further.

| Markdown Headings | Heading Level |
| ----------------- | ------------- |
| Heading 1         | `# H1`        |
| Heading 2         | `## H2`       |
| Heading 3         | `### H3`      |

## Lists

Create a list to organize information.

### Unordered List

An unordered list presents information in no particular order. To create an unordered list, use dashes (`-`), asterisks (`*`), or plus signs (`+`) in front of each line item.

#### Example

`- First item`

`- Second item`

`- Third item`

### Ordered

An ordered list presents information in a specific order for the AI model to process. Unlike the unordered list, the ordered list uses a numerical system to list out line items.

#### Example

`1. First item`

`2. Second item`

`3. Third item`

### Sub-List

Optionally create sub-lists to further organize information. To create sub-lists, indent the sublist items with two spaces.

#### Example

`1. First item`

&#x20;  `- Sub-item 1`

&#x20;  `- Sub-item 2`

`2. Second item`

`3. Third item`

## Bolded Text

Use bolded text to emphasize a section of your Prompt. Bolded text also makes your Prompt more legible for collaborators in your AI.

Create bolded text by using double asterisks (`*`) around the text to bold.

## Other Markdown Syntax

Less frequently used Markdown syntax can help provide examples to the AI model of different types of components or how to generate its output. Examples in your Prompt can help ensure that the initial AI model response is consistent with your instructions.

For example, if you need the AI response to be formatted inside a table, add an example of a table in your Prompt.

| Purpose   | Example                                                                                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Table     | <p><code>Syntax | Description |</code></p><p><code>| ----------- | ----------- |</code></p><p><code>| Header | Title |</code></p><p><code>| Paragraph | Text |</code></p> |
| Task List | <p><code>- [x] Write the press release</code></p><p><code>- [ ] Update the website</code></p><p><code>- [ ] Contact the media</code></p>                                  |
| Link      | `[Text](https://www.example.com)`                                                                                                                                         |
| Image     | `![alt text](image.jpg)`                                                                                                                                                  |
| Image URL | `![alt text](https://imageURL.jpg)`                                                                                                                                       |

For more information on Markdown, see the [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
