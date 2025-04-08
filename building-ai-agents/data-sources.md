---
description: Leverage Retrieval Augmented Generation (RAG) in your AI Agents
---

# Data Sources

A **Data Source** in MindStudio is a repository of files that can be queried by AI workflows to supplement the AI’s responses with domain-specific knowledge. By integrating custom data into your workflows, Data Sources enable **Retrieval Augmented Generation (RAG)**—a method where the AI retrieves relevant information from external data sources to generate more accurate and contextually aware outputs.

When you upload files to a Data Source, they are converted into a vector database. This database allows the AI to query your custom data, retrieve relevant context, and incorporate it into its responses.

## **What is Retrieval Augmented Generation?**

RAG combines AI models with an external knowledge base to enhance the AI's capabilities. Instead of relying solely on pre-trained data, the AI retrieves relevant information from the Data Source and integrates it into its response.

### **How RAG Works**

#### **Knowledge Retrieval**

Before generating a response, the system retrieves relevant information from external sources, such as a knowledge base, database, or documents. This is typically done using vector embeddings and similarity search to find the most relevant pieces of information.

#### **Augmented Generation**

The retrieved knowledge is used as input or context for the AI model during the generation phase. This ensures that the output is informed by domain-specific information, increasing accuracy and relevance.

### **Why Use RAG?**

RAG combines the strengths of retrieval-based systems and generative AI. Instead of relying solely on the model's pre-trained knowledge, it integrates current and specific knowledge at runtime. RAG also reduces hallucinations (making up information) since the generated text is guided by real, retrieved data. Lastly it can handle large, external knowledge bases without the need to retrain all of the information directly as context for the model.

## **Using Data Sources**

To make the AI use a Data Source, you must include a **Query Data Source Block** in your workflow. This block allows you to instruct the AI on how to query the uploaded data and integrate relevant information into its responses.

#### **Example Workflow**:

1. **Upload Product Manuals**: Create a Data Source with PDFs of your product documentation.
2. **Query Data Block**: Use the block to retrieve specific sections based on user queries, such as “How do I reset my device?”
3. **Generate Text Block**: Combine the retrieved data with the AI’s language capabilities to deliver a clear and accurate response.

***

## Automatic Summary Generation

Every file uploaded to a data source is automatically summarized. This summary is created by processing the first few chunks of the document, and it appears on the right side when viewing the document.

<figure><img src="../.gitbook/assets/Access Snippet 3.png" alt=""><figcaption></figcaption></figure>

## Data Source Snippets

### Access Snippet

Users can directly access the full text of any document within a data source. A snippet is displayed on the document view that allows users to copy and retrieve the actual text.&#x20;

This snippet can be used the same as a variable with double curly braces. Example: `{{dataSource "Data_Source_Name" "document.pdf"}}`

<figure><img src="../.gitbook/assets/Access Snippet 1.png" alt=""><figcaption></figcaption></figure>

### Index Snippet

An index snippet lists the names, summaries, and metadata of every file within a single data source. This index can be used as the basis for user input—allowing the system or agents to select the most appropriate document based on a topic.&#x20;

This snippet can be used the same as a variable with double curly braces. Example: `{{dataSource "Data_Source_Name"}}`

<figure><img src="../.gitbook/assets/Index Snippet.png" alt=""><figcaption></figcaption></figure>

***

## Managing Data Sources

### **Create a Data Source**

1. Navigate to the Data Sources Folder from the Explorer Tab
2. Click the **(+) icon** to create a new Data Source.
3. Configure the Data Source with a name and description
4. Upload your files.

#### Supported File Types

* **PDF** (.pdf)
* **CSV** (.csv)
* **Word Document** (.docx)
* **Excel Spreadsheet** (.xlsx)
* **Text File** (.txt)
* **HTML File** (.html)

#### **Limits for Uploads**:

* 500 MB per file
* 5 Million words per file
* Maximum of 150 files per Data Source

{% hint style="warning" %}
**Note:** Uploading files does not automatically make the AI know everything in them.&#x20;

You need to use the [<mark style="color:blue;">Query Data Block</mark>](automations/query-data-block.md) and in order to bring in the context from your Data Source into the workflow.
{% endhint %}

***

## **Managing Data Sources**

### **Viewing Individual Files**

Once a Data Source is created, you can view and explore its individual files to verify the data or ensure that the uploaded content has been processed correctly. Double-clicking on a Data Source opens a detailed view of its contents. When you open a file within a Data Source, the interface provides multiple tabs for exploring different aspects of the data:

* **Preview:** Displays the file preview, giving you a quick way to review the original content. This is useful for verifying that the file has been uploaded correctly.
* **Extracted Text:** Shows the plain text extracted from the file, stripped of any formatting. This is the data the AI will query during workflows.
* **Raw Chunks:** Displays the segmented "chunks" of text that the system uses to create the vector database. Chunks ensure the data is broken down into manageable, queryable parts.
* **Raw Vectors:** Shows the numerical vector representations of the data. These vectors are used by the AI for retrieval during queries.

### **Force Reload a Data Source**

Force reloading ensures that the Data Source reflects the latest changes after you’ve uploaded new or updated files.

1. Open the **Data Sources Folder** in the Explorer Tab.
2. Right-click the Data Source you want to reload.
3. Select **Force Reload** from the drop-down menu.
4. The Data Source will remove all previous data not currently included and update accordingly.

### **Rename a Data Source**

You can rename a Data Source through the Data Source Editor or directly from the Explorer Tab.

**From the Data Source Editor**:

* Open the **Data Sources Folder**.
* Select the Data Source to rename.
* In the editing screen, update the name in the **Name** field.
* Changes are saved automatically.

**From the Explorer Tab**:

* Open the **Data Sources Folder**.
* Right-click the Data Source.
* Select **Rename** and enter the new name in the form field.

### **Delete a Data Source**

1. Open the **Data Sources Folder** in the Explorer Tab.
2. Right-click the Data Source you want to delete.
3. Select **Delete** from the drop-down menu.
4. Confirm the deletion.

***

## **Anatomy of a Data Source**

The **Data Source Details** panel provides an overview of a Data Source's configuration and its current state. This section also includes the **Query Tester**, a tool to verify that your Data Source is properly loaded and functioning as expected.

### **Data Source Details**

This section displays essential information about your Data Source, helping you understand its status and content.

* **Name**: The name of the Data Source. This can be customized to make it easier to identify.
* **Description**: A brief optional description of the Data Source. If no description is provided, it will display as "No description."
* **Status**: Indicates whether the Data Source is loaded and ready for use. Includes a word count progress bar (e.g., "0.1k/5m words") to show how much data has been loaded relative to the word limit.
* **Documents**: The number of files or documents currently included in the Data Source.
* **Words**: The total number of words across all documents in the Data Source.
* **Vectors**: The total number of vectorized entries in the Data Source. Vectors are created during the conversion of documents into a searchable format.

### **Query Tester**

The **Query Tester** is a built-in tool to test queries and validate that your Data Source is working correctly.

* **Query Input**: A text box where you can type your query. This is how you simulate an AI prompt or user question to test the Data Source’s retrieval capabilities.
* **Run Query Button**: Clicking the play button sends the query to the Data Source and returns results, allowing you to verify the response.

#### **Example Use Case**:

If your Data Source contains product manuals, you can test a query like:

```markdown
How do I reset my device?
```

***

## **Data Sources Best Practice**

Data Sources enhance your AI workflows by integrating custom knowledge. Follow these best practices to maximize their effectiveness:

#### **Organize Your Data**

Group related files in the same Data Source for efficient queries and use clear, descriptive names like "Product\_Manuals\_2024."

#### **Prepare Your Files**

Clean files to ensure relevance and accuracy. Use supported formats like PDF, CSV, DOCX, and stay within upload limits (500 MB per file, 150 files per Data Source).

#### **Focus Queries**

Write specific prompts to guide the AI in retrieving the right information. Combine queries with variables for dynamic, context-aware responses.

#### **Keep Data Sources Updated**

Regularly refresh content when information changes and use **Force Reload** to apply updates after modifying or adding files.

#### **Optimize Performance**

Segment large datasets into smaller, focused Data Sources and avoid overloading Data Sources to maintain query accuracy and speed.
