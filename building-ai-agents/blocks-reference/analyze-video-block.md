---
description: Analyze a video URL based on text instructions.
---

# Analyze Video Block

The **Analyze Video Block** processes and analyzes a video URL based on provided text instructions. It generates a text response based on the analysis that is assigned to a variable.

## Configurations

### **Prompt**

Provide text instructions for analyzing the video. Use <mark style="color:red;">`{{variables}}`</mark> to make the prompt dynamic based on a previous step in the workflow.

#### **Example Prompt**:

`Describe what is happening in the video. Focus on the actors and outcome of the video.`

### **Video URL**

Specify the URL of the video to be analyzed. Use a <mark style="color:red;">`{{variable}}`</mark> to dynamically reference the video URL generated or fetched earlier in the workflow.

### **Output Variable**

Creates a new variable and saves the generated video analysis. Enter a <mark style="color:red;">`variable_name`</mark> to store the response for later use in the workflow.

### **Model Settings**

Choose the AI model that you’d like to use for the video analysis. You may adjust the model’s **Temperature** and **Max Response Size**.

## **Writing Video Analysis Prompts**

Creating a well-crafted prompt is essential for accurate and meaningful video analysis. Follow these guidelines to ensure your prompts guide the AI model effectively:

*   **Be Clear and Specific:** Clearly describe what you want the AI to analyze or identify in the video. Focus on specific elements or features relevant to your use case.

    > **Example:** "Identify the main actors in the video, including detailed descriptions, sizes, and positions.”
*   **Define the Objective:** Explain the purpose of the analysis to provide context for the AI. This helps tailor the response to your needs.

    > **Example:** "Analyze the video and describe how to adopt the video flow for a Tik Tok video ad.**”**
*   **Break Down Complex Instructions:** Use simple, step-by-step instructions when requesting detailed analyses.

    > **Example:** " 1. List all objects visible in the video. 2. Describe their positions relative to each other. 3. Describe how the actors interact with each other. 4. Highlight any unusual or standout features.”
*   **Focus on Key Details:** Avoid asking for unnecessary information to keep the analysis concise.

    > **Example:** "Describe the outcome of the video, focusing on actor interaction.”
*   **Include Contextual Cues:** Provide additional context for better results, such as the setting, purpose, or focus of the video.

    > **Example:** "This video shows a park scene. Identify all visible plants, trees, and animals.”
