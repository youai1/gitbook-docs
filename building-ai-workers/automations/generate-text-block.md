---
description: Use an AI model to generate text in your AI Workers.
---

# Generate Text Block

The Generate Text Block sends a text prompt to an AI model and returns the AI Model’s response.

## Configurations

### **Prompt**

Define the instructions sent to the AI model. Use `{{variables}}` to make the prompt dynamic and context-aware.

[Learn about variables →](../variables.md)

### **Response Behavior**

Choose how the AI response is handled:

* **Display to User (Default)**: Shows the response to the end user.
* **Assign to Variable:** Creates a new variable and saves the AI model’s response to it. Enter a `variable_name` \*\*\*\*to store the response for later use in the workflow.

### Output Schema

Choose the format of the AI response:

#### **Text (Default):**&#x20;

Outputs plain or markdown-formatted text, suitable for display or emails.

#### **JSON:**&#x20;

Outputs the response in JSON format, ideal for structured data outputs required for integrations or further processing via code.

**Example Schema:**

```json
{
    "title": "string",
    "summary": "string",
    "date": "string"
}
```

#### **CSV:**&#x20;

Outputs data in CSV format, ideal for tabular data or spreadsheets.

**Example Schema:**

```markdown
Title,Summary,Date
```

For both JSON and CSV outputs, you can explicitly define the output structure by providing a sample output schema.

### **Model Settings**

The default setting is inherited from the underlying model configured in the **Model Settings Tab**. You can override this setting by choosing and configuring a different AI Model specifically for this block.

* **Model Selection**: Choose a different model if needed for the block.
* **Temperature**: Adjust randomness in the response:
  * Lower values = more predictable, consistent results.
  * Higher values = more creative, varied responses.
* **Response Length**: Limit the output size in tokens to suit your needs.

## **Using Conditional Logic in Your Prompt**

The Generate Text Block supports conditional logic to dynamically adjust the text prompt based on workflow variables. This is done using `{{#if}}`, `{{else}}`, and `{{/if}}` statements.

### **How to Use Conditionals**:

#### **Basic Syntax**:

```markdown
{{#if myVariable}}
Use {{myVariable}} to perform this task.
{{else}}
Perform a default action if myVariable is undefined.
{{/if}}
```

**Example:**

```markdown
{{#if customerName}}
Write a thank-you email to {{customerName}}, highlighting our latest offers.
{{else}}
Write a general thank-you email to all customers, highlighting our latest offers.
{{/if}}
```

#### **Nested Conditionals**:

Combine multiple `{{#if}}` statements for complex logic:

```markdown
{{#if userType}}
    {{#if isPremium}}
    Generate a personalized message for our premium user {{userType}}.
    {{else}}
    Generate a message for our standard user {{userType}}.
    {{/if}}
{{else}}
Generate a message for a general audience.
{{/if}}
```
