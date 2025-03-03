---
description: Learn how to properly use dynamic variables in your AI Workflows
---

# Dynamic Variables

Dynamic Variables in MindStudio enable workflows to generate and modify user inputs in real time, allowing for more adaptive and interactive experiences. This feature is particularly useful for scenarios where follow-up questions depend on previous responses, such as product recommendations, lead generation, and troubleshooting agents.

By leveraging **variables, arrays, and Handlebars helpers**, Dynamic Inputs allow workflows to progressively collect information and adjust questions based on user input.

***

### **How Dynamic Inputs Work**

Dynamic Inputs use **variables** to store and retrieve responses, allowing the workflow to adjust its next question dynamically. This pattern is useful in AI Workers that require multiple layers of questioning before generating a final result.

#### **Key Elements**

1. **Inputs Array** – `myVariable[]` - Stores inputs generated into an array.
2. **(optional) User Input Block with Dynamic Prompts** – Add `{{myVariable[]}}` to the title of a [User Input](automations/user-input-block.md)
3. **(optional) Handlebars helpers** - Used to quickly find items in the array variable.

***

### **Building a Workflow with Dynamic Inputs**

#### **1. Collect Initial User Information**

Start by gathering basic user input using a **User Input Block**. This might include general details like name, contact information, or the primary topic of inquiry.

Example:\
&#xNAN;_"What part are you looking for?"_

The response is stored in a **variable**, such as `partRequest`.

***

#### **2. Generate a Follow-Up Question**

Once the user provides an initial answer, the workflow generates a follow-up question based on the input. This follow-up question is:

* **Added to the Questions Array variable:** `questions[]`.
* **Displayed dynamically as the next prompt using:** `{{lastItem questions}}`.

Example:

* The user inputs **"fire sprinkler"**.
* The workflow generates **"What type of sprinkler are you looking for?"** and stores it in `questions`.

***

#### **3. Store User Responses**

Each response is stored in the **Answers Array** Variable (`answers[]`), ensuring all collected data is saved for final processing.

Example:

* The user selects **"Pendant"**, which is added to `answers`.

***

#### **4. (optional) Logic Block for Additional Questions**

The Logic Block determines:

* If more information is needed, the workflow loops back, dynamically generating another follow-up question.
* If sufficient responses are collected, the workflow moves forward to generate the final result.

Example:

* **Second Follow-Up Question:** `"What temperature rating do you need?"`
* **Third Follow-Up Question:** `"What finish or color scheme?"`

***

#### **5. Generate the Final Result**

Once all necessary inputs are collected, the workflow processes the information and generates a response based on the accumulated answers.

Example Output: _"You are looking for a **brass pendant fire sprinkler** with a **135°F** temperature rating."_

***

### **Example: Fire Sprinkler Part Finder**

This workflow dynamically adjusts to refine user requests:

| Step | User Input     | Follow-Up Question                          |
| ---- | -------------- | ------------------------------------------- |
| 1    | Fire Sprinkler | What type of sprinkler are you looking for? |
| 2    | Pendant        | What temperature rating do you need?        |
| 3    | 135°F          | What finish or color scheme do you need?    |
| 4    | Brass          | **Final output is generated**               |

Each follow-up question is stored in `questions[]`, and the corresponding user input is stored in `answers[]`.

***

### **Use Cases for Dynamic Variables**

Dynamic Inputs open new possibilities for AI-driven workflows:

* **Lead Qualification** – Tailor follow-up questions based on user responses to better qualify leads.
* **Product Recommendations** – Ask clarifying questions to suggest the best product options.
* **Troubleshooting Assistants** – Adjust questions dynamically based on user-reported issues.

***

### **Key Takeaways**

* **Dynamic Inputs leverage variables and arrays** to adjust prompts in real time.
* **Follow-up questions are generated and stored in an array**, ensuring adaptability.
* **The Logic Block determines when to stop questioning** and proceed with generating results.
* **Handlebars helpers like `{{last}}` retrieve the most recent question** for dynamic presentation.

This pattern is a **powerful way to build interactive and intelligent AI Workers** that adapt to user needs dynamically. While it requires a deeper understanding of arrays and variable management, the flexibility it provides makes it a game-changer for many AI-driven workflows.
