---
description: Learn how to properly leverage variables in your AI Workflows
---

# Variables

Variables in MindStudio are dynamic placeholders that store data during workflow execution. They allow you to pass information between blocks and workflows seamlessly.

**Example:**

* Variable Name: `userName`
* Usage: `"Hello,`` `<mark style="color:red;">`{{userName}}`</mark>`! Welcome to our app."`&#x20;

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

## Calling Variables

To use a variable in any block or prompt, reference it by enclosing the variable name in double curly braces: `{{variable_name}}`.

**Example Calling Variables in a Generate Text Block**:

```markdown
Summarize the article titled "{{articleTitle}}". 

In the summary, make sure to write about the following topic: 
{{topic}}
```

***

## **Extracting a Value from a JSON Structure**

MindStudio provides tools for extracting specific values from JSON objects using the **JSON Path** syntax and the `get` helper. This allows workflows to handle and manipulate structured data with precision, making them more dynamic and adaptable.

***

### **`get` Helper - Query JSON Variables**

The `get` helper allows you to query JSON variables for specific values using JSON Path expressions. This feature is especially useful when working with nested or complex JSON structures.

#### **Syntax**:

```handlebars
{{get myVariable "$.path.to.value"}}
```

***

#### **Example 1: Extract a Nested Value**:

Given the following  JSON assigned to <mark style="color:red;">`myJsonVariable`</mark>:

```json
{
    "user": {
        "name": "Alice",
        "details": {
            "email": "alice@example.com"
        }
    }
}
```

**Use this to extract the email address:**

```handlebars
{{get myJsonVariable "$.user.details.email"}}
```

**Output**: <mark style="color:blue;">`alice@example.com`</mark>

***

#### **Example 2: Extract the First Item in an Array**:

Given the following JSON:

```json
{
    "items": [
        {"id": 1, "name": "Foo"},
        {"id": 2, "name": "Bar"}
    ]
}
```

Use this to extract the name of the first item:

```handlebars
{{get myJsonVariable "$.items[0].name"}}
```

**Output**: <mark style="color:blue;">`Foo`</mark>

***

#### **Example 3: Extract Multiple Values**:

JSON Path also allows for querying multiple elements. Given the following JSON:

```json
{
    "items": [
        {"id": 1, "name": "Foo"},
        {"id": 2, "name": "Bar"}
    ]
}
```

```handlebars
{{get myJsonVariable "$.items[*].name"}}
```

**Output**: <mark style="color:blue;">`["Foo", "Bar"]`</mark>

***

#### **Best Practices When Extracting JSON**

1. **Use a JSON Path Tester**: Tools like [JSONPath Online Evaluator](https://jsonpath.com/) can help you refine and test your JSON Path queries.
2. **Validate JSON Structure**: Ensure your variable contains valid JSON data before attempting to extract values.
3. **Handle Missing Values**: Include fallback logic in your workflow to handle cases where the expected path does not exist in the JSON.

***

## **Using Handlebars Templating**

MindStudio leverages the [**Handlebars templating language**](https://handlebarsjs.com/guide/expressions.html#basic-usage) to make working with variables intuitive and powerful. Handlebars allows you to include, manipulate, and conditionally render data directly in your prompts, outputs, and logic.

***

### **Conditional Logic**

Handlebars supports `if-else` logic for dynamic outputs:

```markdown
{{#if userName}}
Hello, {{userName}}! How can we assist you today?
{{else}}
Hello! Please log in to get started.
{{/if}}
```

For a full list of expressions, see [Handlebars Documentation](https://handlebarsjs.com/guide/expressions.html#basic-usage).

***

### **Special Handlebars Methods in MindStudio**

In addition to standard Handlebars features, MindStudio introduces two special methods for advanced functionality:

#### <mark style="color:red;">**`{{json varName}}`**</mark>

Converts a JSON object into a string format.

**Example**:

If `userProfile` contains:

```json
{
    "name": "John",
    "age": 30
}
```

**Usage:**

```
{{json userProfile}}
```

**Output:**

```json
{"name":"John","age":30}
```

***

#### <mark style="color:red;">**`{{sample varName number token}}`**</mark>

Extracts a portion of the variable's content based on specified parameters.

* **Parameters**:
  * **varName**: The variable to sample.
  * **number**: The number of items (e.g., lines, words, or letters). If negative, starts from the end.
  * **token**: The type of unit to extract (`line`, `word`, or `letter`).
* **Examples**:
  *   Extract the first 5 words:

      ```
      {{sample textVar 5 word}}
      ```
  *   Extract the last 3 lines:

      ```
      {{sample textVar -3 line}}
      ```
  *   Extract the first 10 letters:

      ```
      {{sample textVar 10 letter}}
      ```
