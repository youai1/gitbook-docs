---
description: Learn about prompt engineering for AI tasks.
---

# Writing Prompts

{% embed url="https://youtu.be/YXK7YpQamiw" %}

Prompts are the foundation of how your AI Agent understands and executes tasks. A well-written prompt ensures your AI Agent delivers precise and meaningful results.

***

## What is a Prompt?

A prompt is a set of instructions that tells the AI Agent what to do. It provides the context and parameters for generating the desired output. Just like giving someone directions, a good prompt ensures the AI knows exactly what to deliver. In MindStudio, prompts can be used at two levels: **System Prompts** and **Block Prompts**.

***

### System Prompt

The System Prompt appears in the **Prompt Tab** of a workflow file. It serves as the AI Agent's core instructions, defining its role, capabilities, and constraints and acts as the foundation, guiding how the AI behaves throughout the workflow.

When you write a system prompt, you’re establishing the AI's "role" and general approach to tasks. Every action in the workflow will follow this overarching guidance unless overridden by specific block prompts.

You can write a system prompt manually by typing into the blank space of the **Prompt Tab**, or you can click on the **Generate Prompt** button at the bottom left to have the **Prompt Generator** to write the prompt for you.

#### Using the Prompt Generator

1. Click on the **Generate Prompt** button at the bottom left of the prompt area. This will open the Prompt Generator Modal.
2. Using natural language, enter a brief description of what your AI Agent is supposed to do.
   1.  **Example:**

       {% code overflow="wrap" %}
       ```markdown
       Assistant finds daily technology news, summarize it, and send an email at 8:00 AM. It includes up-to-date, and accurate information based on the context it is provided.
       ```
       {% endcode %}
3. After entering your description, click the **Generate** button. The system will automatically create a structured prompt based on your input.
4. Carefully review the generated prompt to make sure it aligns with your requirements. You can edit the prompt directly in the editor if adjustments are needed.

***

### Block Prompt

A **block prompt** is used for specific tasks within the workflow. While the system prompt provides overall guidance, a block prompt gives detailed instructions for a particular step.

**Example of a Block Prompt (within a Generate Text block):**

{% code overflow="wrap" %}
```markdown
Summarize the following news articles: {{google_result}}.
```
{% endcode %}

Here, the block prompt tells the AI to focus on summarizing a specific piece of information (e.g., the result of a Google search). This allows you to customize how the AI performs at different stages of the workflow.

#### **How System Prompts and Block Prompts Work Together**

| System Prompt                                                                                       | Block Prompt                                                                                             |
| --------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Purpose:** Acts like the big picture instruction. It’s the AI’s mindset for the entire workflow.  | **Purpose:** Adds specific, step-by-step instructions for individual tasks.                              |
| **Example:** "You are a tech-savvy assistant that simplifies complex topics for general audiences.” | **Example:** "Write a one-paragraph summary of the latest AI breakthrough using non-technical language." |

***

### Key Aspects of Prompt Writing

A good prompt is clear, specific, and provides enough context for the AI to understand what’s needed.

#### **Key aspects of an effective Prompts:**

* **Clarity**: Use straightforward language to avoid confusion. Clearly define the AI Agent's purpose and main tasks
* **Specificity**: Be detailed about what you want. Specify any limitations or guidelines that your AI Agent should follow when executing its task
* **Context**: Explain the purpose or provide a scenario to guide the AI. Context can be provided via direct instruction or by calling Variables within a prompt.
* **Output Format**: Outline the expected format or structure of its output.

#### **Examples of Good Prompts vs. Bad Prompts**

| Scenario                   | Good Prompt                                                                                         | Bad Prompt                           |
| -------------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------ |
| **Summarizing an Article** | "Summarize this article in 3 bullet points, focusing on key trends in technology."                  | "Summarize this."                    |
| **Writing an Email**       | "Write a professional email to a client, introducing our new AI tool and inviting them for a demo." | "Write an email about our product."  |
| **Data Analysis**          | "Analyze the provided sales data and list the top 3 trends for Q4 in bullet points."                | "Analyze this data."                 |
| **Creative Writing**       | "Write a 150-word humorous story about a robot learning to make ice cream."                         | "Write a funny story about a robot." |

***

## **Using Markdown to Write Prompts**

Markdown is a lightweight formatting language that can be used to structure prompts, making them clearer and easier for the AI to interpret. By using Markdown, you can organize your instructions in a readable and visually structured way.

### **Why Use Markdown in Prompts?**

1. **Clarity**: Break down complex instructions into digestible sections.
2. **Readability**: Using formatting like headers, bullet points, and code blocks to make prompts easier to follow.
3. **Consistency**: Ensure your prompt has a standardized structure, especially for complex tasks.
4. **Debugging:** Allows for easier debugging and refinement of prompts.

### **Common Markdown Elements for Prompts**

Here are some common Markdown features and how to use them:

1. **Headers**
   * **Purpose:** Use headers to introduce sections or tasks.
   * **Variations:**
     * `#` for H1
     * `##` for H2
     * `###` for H3
     * `####` for H4
   *   Example:

       ```markdown
       # Task: Summarize the Article
       ```
2. **Bullet Points**
   * **Purpose:** Break down requirements into bullet points for clarity.
   *   Example:

       ```markdown
       - Summarize the following text.
       - Highlight key trends in technology.
       - Keep the summary under 100 words.
       ```
3. **Numbered Lists**
   * **Purpose:** Use for step-by-step instructions.
   *   Example:

       ```markdown
       1. Analyze the data provided.
       2. Identify the top three trends.
       3. Provide a summary in bullet points.
       ```
4. **Code Blocks**
   * **Purpose:** Use code blocks for examples or templates.
   *   Example:

       ````markdown
       ```json
       {
           "topic": "daily tech news",
           "summary_length": "3 sentences"
       }
       ````
5. **Bold and Italics**
   * **Purpose:** Emphasize key instructions.
   *   Example:

       ```markdown
       **Focus on key trends only.**
       *Avoid including minor details.*
       ```

***

**Example System Prompt Using Markdown**

````markdown

# Daily Tech News Assistant

## Role:
You are an AI assistant designed to summarize daily technology news for a non-technical audience. Your goal is to deliver concise, accurate, and well-structured summaries.

---

## Guidelines:
- Focus on **key trends and developments** in technology.
- Summaries must be written in simple, clear language suitable for readers with no technical background.
- Avoid including unnecessary details or jargon.

---

## Tasks:
1. Perform a search for the latest **technology news** based on the provided topic.
2. Summarize the articles into concise bullet points.
3. Format the output in the specified structure.

---

## Output Format:
The summary should be formatted as follows:

```markdown
### Daily Tech News Summary
1. [Key Trend 1]
2. [Key Trend 2]
3. [Key Trend 3]
````

For more information on Markdown, see the [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

***

### Auto-Enhance Prompts

The Auto-Enhance feature helps polish and refine your prompts after you've made modifications. It analyzes your prompt for clarity, formatting, and potential ambiguities, then suggests improvements while maintaining your original intent.

<figure><img src="../.gitbook/assets/Screenshot 2024-12-03 at 3.28.44 PM.png" alt=""><figcaption></figcaption></figure>

#### How Auto-Enhance Works

1. **Access the feature:** Click the "Enhance" button in the bottom bar or use the keyboard shortcut Option + K
2. **Review suggestions:** The system presents an enhanced version of your prompt with improvements in:
   * Grammar and spelling
   * Markdown formatting consistency
   * Clarity and precision of instructions
   * Structure and organization
3. **Accept or reject changes:** Choose whether to implement the suggested improvements

This feature works both in the main **Prompt Tab** and in fullscreen **Send Message blocks**, making it easy to maintain high-quality prompts throughout your workflow.

{% hint style="info" %}
**Pro Tip:** Auto-Enhance is particularly useful when you've started with a generated prompt and made manual modifications, helping ensure your customizations maintain professional quality and clarity.
{% endhint %}

Creating a structured template lets the model knows exactly **where** and **how** to inject content. By pairing a template with your data, you get consistent, predictable results every time.

***

## Writing Templates

A template is a block of text (in Markdown, HTML, or JSON) containing **placeholders** for your variables. When your workflow runs, MindStudio replaces those placeholders with the actual values you’ve collected (via user inputs, scraped data, files, etc.) and sends the combined prompt to the model.

* **Placeholders** can use either XML-style tags <mark style="color:red;">`<company>…</company>`</mark> or square-bracket notation <mark style="color:red;">`[company]`</mark>.
* Inside a Generate Text or Generate Asset block, you supply:
  1. **Your data** (e.g., user inputs saved to variables)
  2. **The template** itself
* The model fills each placeholder according to your template’s structure.

***

### Why Use Templates?

* **Consistency**: Ensure every output follows the same format.
* **Clarity**: Guide the model step-by-step—no guessing about headings, sections, or order.
* **Scalability**: One template handles countless inputs.
* **Flexibility**: Swap templates for different formats (HTML vs. Markdown vs. JSON) without rewriting your workflow.

***

### Writing Templates

#### **Using Square Bracket Notation**

Square brackets are ideal for quick and easy placeholders in Markdown templates or ad-hoc prompts. They are simple to identify in plain text and work best when you have single-word placeholders like <mark style="color:red;">`[title]`</mark> or <mark style="color:red;">`[body]`</mark>.&#x20;

Use them when writing short, straightforward templates, such as bullet lists or paragraphs, where the format resembles a "fill-in-the-blanks" approach.

**Example prompt that uses Square brackets:**

```markdown
Write a blog post about {{blogTopic}}. Use Markdown.

[Blog Title]

[Hook+Context]

[Main Point 1]
- [Supporting Detail]
- [Example]

[Main Point 2]
- [Supporting Detail]
- [Example]

[Summary + Call to Action]
```

#### **Using XML Tags**

XML-style tags clearly show where each placeholder starts and ends to help avoid confusion with nearby text or symbols. This is particularly helpful for making sure variables are clearly displayed to the AI model.&#x20;

**Prompt Example (Generate Blog Post):**

```markdown
Write a blog post using Markdown.

<topic>
{{blog_topic}}
</topic>
```

You can also use them when you have longer placeholders, or for creating HTML templates with the **Generate Asset block**.

**HTML Example (Marketing Email):**

{% code overflow="wrap" %}
```html
<html>
  <body>
    <h1>Hey <recipient_name>{{name}}</recipient_name>,</h1>
    <p>We’re excited to introduce <product_name>{{product}}</product_name>—<product_tagline>{{tagline}}</product_tagline>.</p>
    <ul>
      <li><feature_1>{{feature_1}}</feature_1></li>
      <li><feature_2>{{feature_2}}</feature_1></li>
    </ul>
    <p><cta_text>{{CTA}}</cta_text></p>
  </body>
</html>
```
{% endcode %}

{% hint style="info" %}
For more information on creating HTML templates please review the [Generate Asset block](blocks-reference/generate-asset-block.md) article.
{% endhint %}

***

### Best Practices for Template Writing

* **Name your placeholders** clearly (e.g. <mark style="color:red;">`[project_summary]`</mark>, not <mark style="color:red;">`[x]`</mark>).
* **Wrap variables** in tags to avoid ambiguity <mark style="color:red;">`<budget>{{budgetVariable}}<budget>`</mark> .
* **Test incrementally**: start with one section, preview, then expand.
* **Use Markdown** for quick proofs; **HTML** when you need precise styling.
