---
description: Learn how to properly leverage variables in your AI Workflows
---

# Variables

Variables in MindStudio are dynamic placeholders that store data during workflow execution. They allow you to pass information between blocks and workflows seamlessly.

**Example:**

* Variable Name: `userName`
* Usage: `"Hello {{username}}! Welcome to our app."`&#x20;

***

## Creating Variables

Variables are created automatically in MindStudio whenever:

* A **User Input** collects data.
* A block generates an output (e.g., **Generate Text Block**, **Analyze Image Block**).
* You manually define them in the **Start Block**.

***

## **Types of Variables**

### **Launch Variables**

These are defined in the **Start Block** of your workflow. Values for these variables are passed in as arguments when a workflow is run via API or via the Run Workflow block.

### **Runtime Variables**

Some blocks, such as **Generate Text Blocks** or **User Input Blocks**, assign values for the variable while the workflow is running. For Example, after performing a Google Search, the block can store the results in a variable called `google_result`.

***

## Using Variables

To use a variable in any block or prompt, reference it by enclosing the variable name in double curly braces: `{{variable_name}}`.

**Example Using Variables in a Generate Text Block**:

```markdown
Summarize the article titled "{{articleTitle}}". 

In the summary, make sure to write about the following topic: 
{{topic}}
```

***

## Tips for Working with Large Variables

Variables are replaced with their values before the text is sent to the AI model. You must make sure your message will be coherent and legible after the variables have been substituted with their values. For longer variables, this means using things like XML tags to offset variable content from instructions.

**Incorrect:**

```
Summarize this article {{articleContent}} and find all mentions of {{personName}}.
```

This pattern does not work because `{{articleContent}}` will be replaced with the raw text or HTML of an article. If you execute this prompt and view its logs in the [Debugger](../../test-and-evaluate/debugger.md), you will see that what is sent to the model is a giant sentence like "Summarize this article The history of lorem ipsum has long been thought to contain dolor sit amet \[...1000 more words from the article directly pasted in] and find all mentions of Taylor Swift".&#x20;

While AI models are great at parsing text, using simple formatting can make prompts dramatically more effective, as well as easier for you to maintain.

**Correct:**

```
<article_content>
{{articleContent}}
</article_content>

Using the provided article content, create a summary of the article as well as a list of all mentions of {{personName}}.
```

Offsetting with XML-style tags (it doesn't matter what the actual tags are, you can make up anything you like as long as it makes sense) helps the model understand which aspects of your prompt are instructions and which are context. [Anthropic](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/long-context-tips#example-quote-extraction) found that placing long variables at the top of the prompt using XML tags improved response quality by up to 30%.

To achieve best results, you should strive to make your prompt as easy to read for a human as possible. A handy test is to imagine that you were to print out your prompt on paper (after all variables have been substituted) and give it to someone. Would they be able to understand what you want them to do? Or would it look like gibberish?
