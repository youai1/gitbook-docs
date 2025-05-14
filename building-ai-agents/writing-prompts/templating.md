---
description: Create templates that define the structure of your AI agent's output.
---

# Templating

Creating a structured template lets the model knows exactly **where** and **how** to inject content. By pairing a template with your data, you get consistent, predictable results every time.

## What Is a Template?

A template is a block of text (in Markdown, HTML, or JSON) containing **placeholders** for your variables. When your workflow runs, MindStudio replaces those placeholders with the actual values you’ve collected (via user inputs, scraped data, files, etc.) and sends the combined prompt to the model.

* **Placeholders** can use either XML-style tags <mark style="color:red;">`<company>…</company>`</mark> or square-bracket notation <mark style="color:red;">`[company]`</mark>.
* Inside a Generate Text or Generate Asset block, you supply:
  1. **Your data** (e.g., user inputs saved to variables)
  2. **The template** itself
* The model fills each placeholder according to your template’s structure.

***

## Why Use Templates?

* **Consistency**: Ensure every output follows the same format.
* **Clarity**: Guide the model step-by-step—no guessing about headings, sections, or order.
* **Scalability**: One template handles countless inputs.
* **Flexibility**: Swap templates for different formats (HTML vs. Markdown vs. JSON) without rewriting your workflow.

***

## Creating a Template

### **Using Square Bracket Notation**

Square brackets are ideal for quick and easy placeholders in Markdown templates or ad-hoc prompts. They are simple to identify in plain text and work best when you have single-word placeholders like <mark style="color:red;">`[title]`</mark> or <mark style="color:red;">`[body]`</mark>.&#x20;

Use them when writing short, straightforward templates, such as bullet lists or paragraphs, where the format resembles a "fill-in-the-blanks" approach.

#### Example prompt that uses Square brackets:

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

{% hint style="info" %}
For more information on using Markdown, please review the [Writing Prompts](./) article.
{% endhint %}

### **Using XML Tags**

XML-style tags clearly show where each placeholder starts and ends to help avoid confusion with nearby text or symbols. This is particularly helpful for making sure variables are clearly displayed to the AI model.&#x20;

#### Prompt Example (Generate Blog Post):

```markdown
Write a blog post using Markdown.

<topic>{{blog_topic}}</topic>
```

You can also use them when you have longer placeholders, or for creating HTML templates with the **Generate Asset block**.

#### HTML Example (Marketing Email):

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
For more information on creating HTML templates please review the [Generate Asset block](../automations/generate-asset-block.md) article.
{% endhint %}

***

## Best Practices

* **Name your placeholders** clearly (e.g. <mark style="color:red;">`[project_summary]`</mark>, not <mark style="color:red;">`[x]`</mark>).
* **Wrap variables** in tags to avoid ambiguity <mark style="color:red;">`<budget>{{budgetVariable}}<budget>`</mark> .
* **Test incrementally**: start with one section, preview, then expand.
* **Use Markdown** for quick proofs; **HTML** when you need precise styling.
