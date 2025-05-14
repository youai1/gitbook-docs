---
description: Learn about structured data with JSON.
---

# Working with JSON

## What Is JSON in MindStudio?

* **JSON** (JavaScript Object Notation) is a lightweight data-interchange format
* JSON lets you structure AI output as **key–value pairs**, making it easy to parse, display, or export to other systems.
* Represents data as nested **objects** and **arrays**
* Ideal for:
  * Structured reports or catalogs
  * Data exports (to CSV, spreadsheets, databases)
  * Downstream logic (conditionals, integrations)

### JSON Fundamentals Cheat-Sheet

| Syntax          | Meaning                                  |
| --------------- | ---------------------------------------- |
| `{ … }`         | **Object** (holds key–value pairs)       |
| `"key": value,` | **Key–value pair** (separated by commas) |
| `"string"`      | **String** (always in quotes)            |
| `123`           | **Number** (no quotes)                   |
| `true`/`false`  | **Boolean**                              |
| `[ … ]`         | **Array** (ordered list of items)        |

***

## Enable JSON Output

Open your **Generate Text** block.

Under **Output Schema**, select **JSON** instead of Text. A **Sample Output** editor appears—this is where you define your JSON template.

<figure><img src="../../.gitbook/assets/JSON IMG.png" alt=""><figcaption></figcaption></figure>

## Define Your JSON Template

In **Sample Output**, sketch the shape of your response:

```json
{
  "title": "Strong, provocative",
  "subtitle": "",
  "body": "Up to 50 words",
  "call_to_action": "",
  "image_prompt": "Prompt for AI to generate background image"
}
```

* **Keys** (e.g., <mark style="color:red;">`title`</mark>, <mark style="color:red;">`body`</mark>) define fields your AI will fill.
* **Values** can be placeholders or examples guiding the model’s output.
* **Empty strings** (<mark style="color:red;">`""`</mark>) let the AI choose content freely.

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
