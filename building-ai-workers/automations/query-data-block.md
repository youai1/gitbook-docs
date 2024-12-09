---
description: Integrate custom data into your AI workflows using RAG
---

# Query Data Block

The **Query Data Source Block** allows you to retrieve relevant information from a [Data Source](../data-sources.md) within your workflow. This block is essential for integrating custom data into your AI workflows through Retrieval Augmented Generation (RAG).

***

## **Configurations**

### **Data Source**

Select the Data Source you want to query. This is the collection of documents you have uploaded and configured in the **Data Sources Folder**.

#### **Options**

* Use the dropdown menu to select an existing Data Source.
* Click **New...** to create a new Data Source if none are currently available.

### **Variable Name**

Creates a variable where the query results will be stored. Enter a <mark style="color:red;">`variable_name`</mark> to store the result of the query for later use in the workflow.

### **Max Results**

Define the number of results the block will retrieve from the Data Source. Each result will return a different chunk of retrieved text from the Data Source.

### **Query Template**

Enter the query prompt that instructs the AI on what information to retrieve. You can include <mark style="color:red;">`{{variables}}`</mark> to make the query dynamic and context-aware.

[Learn about variables →](../variables.md)

***

## **Writing Effective Queries**

Crafting effective queries is crucial for retrieving the most relevant and accurate information from your Data Sources. A well-written query ensures that your AI can efficiently locate and use the data needed for your workflow.

#### **Understand Your Data Source**

Familiarize yourself with the content of your Data Source. Knowing the structure, topics, and focus of the documents helps you write more precise queries.

**Example:**

If your Data Source contains product manuals, your queries should explicitly reference product names or sections like "warranty" or "setup instructions."

#### **Be Clear and Specific**

Write concise and focused queries to ensure the AI retrieves the most relevant results. Avoid overly broad or ambiguous prompts.

**Examples**:

* **Broad Query**: `Tell me about this product.`
* **Specific Query**: `What are the warranty terms for the {{productName}}?`

#### **Use Contextual Language**

Include specific instructions or context in your query to guide the retrieval process.

**Examples**:

```markdown
Find troubleshooting steps for {{deviceName}} related to connectivity issues.
```

```markdown
Retrieve all safety precautions mentioned in the {{documentType}}.
```

#### **Limit Query Scope**

Tailor the query to focus on a specific part of the Data Source to improve accuracy. For large Data Sources, specifying a topic or section can yield better results.

**Example**:

```
Search the "user guide" section for instructions on resetting the {{productName}}.
```

#### **Include Actionable Keywords**

Use actionable keywords like "retrieve," "explain," "summarize," or "list" to make the purpose of the query clear.

**Examples**:

```markdown
"Summarize the maintenance steps for the {{productName}}."
```

```markdown
"List all recommended accessories for {{productName}}."
```

#### **Test and Refine**

Test your query with the [Query Tester](../data-sources.md#query-tester) to ensure it retrieves the intended results. Adjust the wording, variables, or focus as necessary.
