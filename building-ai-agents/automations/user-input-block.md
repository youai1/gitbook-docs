---
description: Collect data directly from end users
---

# User Input Block

{% embed url="https://youtu.be/p28WmgLd8ZU" %}

The **User Input Block** lets your workflows to collect data directly from end users. Unlike AI-focused blocks, this block presents the forms or interfaces where users can provide input. When New User Inputs are automatically added to the **User Inputs** folder in the left-side **Explorer** tab.

## What is a User Input?

A **User Input** in MindStudio is a form-based interface that collects data directly from your end users. This data serves as context or input for workflows, and is stored as a `variable` and serves as context for downstream processes and AI-powered actions within your workflow .

When New User Inputs are created, they are automatically added to the **User Inputs** folder in the left-side **Explorer** tab.

## Add Existing User Inputs

1. Click on the + button at the bottom of the User Inputs Configuration Panel.
2. In the modal, choose from created User Inputs to add to the block.
3. (Optional) Click and drag User Inputs up and down to reorder them.
4. Click the **Add** button to confirm your choices.

## Create A New User Input

#### **From the User Input Block:**

1. Click on the (+) button at the bottom of the User Inputs Configuration Panel.
2. In the modal, click the **Create New**… button at the bottom left. A new User Input will be created in Explorer within the User Inputs folder, **and will be automatically added to the block**.
3. Configure the user input.

#### **From the Explorer:**

1. Hover over the User Inputs folder, then click on the + button to the right of the folder. A new User Input will be created in Explorer within the User Inputs folder.
2. Configure your User Input.
3. After configuring the User Input, you will need to add the User Input to the User Input Block.

## Edit A User Input

1. Open the **User Inputs** folder from the **Explorer** tab.
2. Click on the User Input that you’d like to modify
3. Changes to configurations are automatically saved.

## **Duplicate a User Input**

1. Open the **User Inputs** folder in the **Explorer** tab.
2. Right-click on the User Input to duplicate.
3. Select the **Duplicate** option.

The duplicated User Input displays in the **User Input** folder using the root name of the original with a number following it.

### **Delete a User Input**

Deleting a User Input removes it from all User Input Blocks across all Workflows.

1. Open the **User Input** folder in the **Explorer** tab.
2. Right-click on the User Input to delete.
3. Select the **Delete** option from the drop-down menu.
4. Confirm your deletion.

***

## Anatomy of a User Input

### Type

The type of User Input determines its functionality and format. See the table below for a full list of User Input types.

| Input Type       | Description                                                                                                  | Best For                                      | Example                                              |
| ---------------- | ------------------------------------------------------------------------------------------------------------ | --------------------------------------------- | ---------------------------------------------------- |
| **Short Text**   | Collects small amounts of text for concise inputs.                                                           | Names, URLs, locations.                       | "Enter your city."                                   |
| **Long Text**    | Collects large amounts of text, such as detailed descriptions or pasted content.                             | Long-form responses, content uploads.         | "Describe your project in detail."                   |
| **Text Choice**  | Allows users to select one or multiple text-based choices.                                                   | Yes/No questions, multiple-choice selections. | "Which services do you use? (Select all that apply)" |
| **Image Choice** | Enables selection of one or multiple images, each labeled with text.                                         | Visual comparisons or preferences.            | "Select your preferred design."                      |
| **Rating**       | Provides a 1–5 scale rating input.                                                                           | Feedback or satisfaction scoring.             | "Rate our service (1=Poor, 5=Excellent)."            |
| **Date**         | Displays a date picker for selecting specific dates.                                                         | Scheduling or logging events.                 | "Select your appointment date.”                      |
| **Display**      | Shows static text or images for guidance or instructions. No user input required.                            | Providing information or directing users.     | "Enter a URL to analyze the page content.”           |
| **Upload File**  | Presents an upload option for text-based files. Supported formats include Excel, CSV, Word, Text, PDF, HTML. | Uploading documents for AI analysis.          | "Upload your report for review.”                     |
| **Upload Image** | Allows users to upload images for analysis or storage.                                                       | Collecting visual content or custom inputs.   | "Upload an example visual."                          |

### Variable

The <mark style="color:red;">`variable_name`</mark> is a unique identifier for the User Input. It is used to reference the collected data in downstream workflow blocks. Use a variable name that is unique to the data being collected. (**Example:** <mark style="color:red;">`customer_goal`</mark> , <mark style="color:red;">`client_industry`</mark> , <mark style="color:red;">`first_name`</mark> )

### Multiple File Upload

The User Input block allows for multiple file upload. Multiple files are stored in one JSON variable via index. **Example**: <mark style="color:red;">`[0: file 1 extracted text, 1: file 2 extracted text]`</mark>

You can extract the contents of each file by using the proper [JSON structure variable syntax.](../variables/#extracting-a-value-from-a-json-structure)

### Configurations

Configurations define how the User Input behaves and what options are available. These settings vary depending on the input type.

### Featured Image

An optional image displayed above the input field when presented to the end user. It enhances visual appeal and provides context to your end user.

### Test Value

Pre-fills the input field with a sample response when previewing workflows. This simplifies front-end testing when viewing a draft preview of an AI Agent.
