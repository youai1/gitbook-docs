---
description: Follow best practices to write Prompts for your MindStudio AIs.
---

# Best Practices for Writing Prompts

## Best Practices to Structure Your Prompt

* Organize your [Prompt](what-is-a-prompt.md) into sections using Markdown. See this [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
* Structure your Prompt, as needed, into the following Heading 1 sections. Within each section, write each descriptor or instruction in an unordered list.

### Purpose

The Purpose section describes the goal(s) the AI app solves. Why are you creating this app? Explicitly describe the app's purpose and the actors involved.

#### Best Practices

* Your app involves at least two actors: the AI model and the app's user. In the Prompt, refer to the AI model as Assistant. Refer to the user as Human.
* Explicitly state in the first listed item in the Purpose section that Assistant is the app and what that app does. For example, Assistant is an app that generates blog posts for users.

### Context

The Context section describes any additional information, context, or background to inform the AI model how to perform the task(s).

#### Best Practices

* Contextual information ensures that the AI model processes it completely. Contextual information can go into a [Data Source](../data-sources/what-is-a-data-source.md). If the contextual information is important and is between 200,000 and 240,000 characters (including spaces), then include it into the Prompt.
* If the contextual information is not important and is greater than 240,000 characters, then add as a file into a Data Source.

### Examples

The Examples section provides explicit examples from which the AI model can generate its response. Examples are required when using the [Chain-of-Thought (CoT) prompting technique](chain-of-thought-prompt-writing-technique.md).

### Tasks

The Tasks section explicitly instructs the tasks that the app performs.

#### Best Practice

Describe upon which actor the AI model performs the task. For example, does the AI model submit a message to Human (app user) or to another explicitly stated system? If the latter, ensure that the stated system is explicitly described as an actor in the Purpose section.

### Parameters

The Parameters section specifies the conditions under which the AI model operates to fulfill the Prompt's instructions. This section plays a crucial role in guiding the AI model’s response by defining the boundaries and specifics of the task(s).

### Output

The Output section specifies the expected results from the AI model’s processing of the Prompt. This section outlines the specific characteristics, format, and content that you expect in the AI's response.

#### Best Practices

* Explicitly specify information or content that must be included in the AI model’s response. This section guides the AI regarding what topics, points, or data should be in the output to ensure it is relevant and comprehensive. This is particularly important for Prompts to generate informative or educational content.
* Specify the presentation format of the output if necessary. For example, should the output be a list, table, or a specific document structure?
* Specify the file type to output if necessary. For example, should the output be in plain text, CSV, PDF, HTML, or other format?

### Traits

The Traits section specifies the desired characteristics, tone, style, and other qualitative aspects of the AI model's response. This section ensures the AI model’s response aligns with your expectations in terms of presentation, voice, and overall feel.

### Constraints

The Constraints section restricts the AI model's response and output by setting specific rules or conditions. This section ensures that the AI's responses narrows the output to be more predictable, relevant, and aligned with your use case. Constraints streamline the AI model's processing by limiting the scope of its responses.

#### Best Practices

* Specify topics or themes that should be included or avoided in the AI model's response. This tailors the content to your preferences and avoids irrelevant topics.
* In use cases where the AI model is assigned a specific role (such as a tutor, advisor, coach, or co-pilot), constraints define how it should behave within that role to maintain consistency and appropriateness.
* Specify the sources the AI model can or cannot use for generating responses. This is crucial to ensure the credibility and accuracy of the information provided.
* Limit the length of the AI model’s responses to ensure brevity and conciseness. This is particularly useful for tasks where information needs to be succinct.

## Prompt Writing Style Best Practices

* Use clear and concise language in your Prompts to avoid ambiguity.
* Keep your Prompts simple and straightforward. State one idea at a time.
* Avoid repetitive lines, grammatically incorrect sentences, or the same [Variable](../user-inputs-and-variables/what-is-a-variable.md) repetitively. This writing style can overwhelm the AI model and cause issues.

## Best Practices to Reference Variables

### Reference a Variable Once

Reference a Variable once in the Prompt. Referencing a Variable more than once may overload the AI model or cause hallucinations or other undesirable responses.

Compare the examples below how not to use a Variable in a Prompt versus how to do so. In these examples, the Variable is named style. Placing the Variable name between double curly braces injects the data the Variable stores into the Prompt and replaces the text \{{style\}}. Note how in the improper example, after the Variable value is injected into the Prompt, the instruction becomes grammatically incorrect, thereby making it unlikely the AI model understands the instruction.

#### Bad Practice

After the Variable value is injected into the Prompt, the instruction becomes grammatically incorrect, thereby making it unlikely the LLM understands the instruction.

{% code overflow="wrap" %}
```
/The Assistant is a Copy Writer that assists Human in generating SEO-focused Blog Posts in the writing {{style}} of Human.
```
{% endcode %}

#### Best Practice

Write the Variable after a colon (`:`) so that after the Variable value is injected into the Prompt, the instruction remains grammatically correct and clear.

{% code overflow="wrap" %}
```
The Assistant is a Copy Writer that assists Human in generating SEO-focused Blog Posts in the writing style of Human.
The Assistant understands Human’s writing style as: {{style}}.
```
{% endcode %}

## Address the AI in the Prompt in the Third-Person Perspective

When writing your Prompt, address the AI model in the third person, not in second person. Addressing the AI in third person instructs the AI what role to assume so as to perform the subsequent instruction(s) that follow. Providing the AI model which role to assume sets the context for which data the AI model has at its disposal.

### Bad Practice

This improperly written Prompt addresses the AI model in the second person perspective.

{% code overflow="wrap" %}
```
You are a Youtube Metadata Generator that generates Metadata for Youtube videos.
```
{% endcode %}

### Best Practice

This properly written Prompt addresses the AI model in the third person perspective. Note how the AI is referred to as Assistant, which is also a best practice.

{% code overflow="wrap" %}
```
The Assistant is a Youtube Metadata Generator that assists Human in generating metadata for their Youtube videos.
```
{% endcode %}

## Save Certain Actions for Automations

Not all instructions belong in the Prompt. As a best practice, use the Prompt to define the AI model’s role and designated task(s). Specific actions belong in your [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md).

### Bad Practice

This improperly written Prompt instructs which action the LLM (AI model) should take. Instead, use a Send Message Block in the Automation Workflow that outputs the response of that message directly to the app user.

{% code overflow="wrap" %}
```
The Assistant is a LinkedIn Post Generator that assists Human with generating a LinkedIn Post article about: {{topic}}.
```
{% endcode %}

### Best Practice

This properly written Prompt does not specify which action to take.

{% code overflow="wrap" %}
```
Write a LinkedIn post article about: {{topic}}.
```
{% endcode %}
