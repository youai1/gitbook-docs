---
description: Build a MindStudio AI that automates basic Google searches.
---

# Google Basic Search: Custom Function

## What is Google Basic Search?

[Google](https://www.google.com/) provides both basic and advanced search capabilities.

## What Can I Do With MindStudio and Google Basic Search?

Build a MindStudio AI that automates basic Google searches.

## What is Required for This Custom Function?

* **Google Search - Basic** Custom Function.

## Configuration

### Search Query

Enter the search query to send to Google. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores the entire or partial search query in a User Input provided by the user.

**Example of a Variable containing the entire search query:**

```
{{Search}}
```

**Example of a Variable containing the partial search query:**

{% code overflow="wrap" %}
```
Specify the most relevant SEO marketing keywords in the following industry: {{Industry}}
```
{% endcode %}

### Output Variable

Enter the Variable that stores Google’s response. **Example:**

```
{{Response}}
```
