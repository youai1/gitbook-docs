---
description: Analyze an image URL based on text instructions.
---

# Analyze Image Block

The **Analyze Image Block** processes and analyzes an image URL based on provided text instructions. It generates a text response based on the analysis that is assigned to a variable.

## Configurations

### **Prompt**

Provide text instructions for analyzing the image. Use <mark style="color:red;">`{{variables}}`</mark> to make the prompt dynamic based on a previous step in the workflow.

#### **Example Prompt**:

{% code overflow="wrap" %}
```markdown
Identify the objects in the image and describe their arrangement. Focus on colors and sizes.
```
{% endcode %}

### **Image URL**

Specify the URL of the image to be analyzed. Use a <mark style="color:red;">`{{variable}}`</mark> to dynamically reference image URL generated or fetched earlier in the workflow.

### **Output Variable**

Creates a new variable and saves the generated test response to it. Enter a <mark style="color:red;">`variable_name`</mark> to store the response for later use in the workflow.

### **Model Settings**

Choose the AI Model that you’d like to use for the image analysis. You may adjust the model’s **Temperature** and **Max Response Size**.

## **Writing Image Analysis Prompts**

Creating a well-crafted prompt is essential for accurate and meaningful image analysis. Follow these guidelines to ensure your prompts guide the AI model effectively:

*   **Be Clear and Specific:** Clearly describe what you want the AI to analyze or identify in the image. Focus on specific elements or features relevant to your use case.

    > **Example:** "Identify the main objects in the image, including their colors, sizes, and positions.”
*   **Define the Objective:** Explain the purpose of the analysis to provide context for the AI. This helps tailor the response to your needs.

    > **Example:** "Analyze the image and describe how the objects are arranged for interior design recommendations.**”**
*   **Break Down Complex Instructions:** Use simple, step-by-step instructions when requesting detailed analyses.

    > **Example:** " 1. List all objects visible in the image. 2. Describe their positions relative to each other. 3. Highlight any unusual or standout features.”
*   **Focus on Key Details:** Avoid asking for unnecessary information to keep the analysis concise.

    > **Example:** "Describe the objects on the table, focusing on their materials and colors.”
*   **Include Contextual Cues:** Provide additional context for better results, such as the setting, purpose, or focus of the image.

    > **Example:** "This image shows a park scene. Identify all visible plants, trees, and animals.”
