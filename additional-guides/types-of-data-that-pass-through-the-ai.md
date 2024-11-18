---
description: >-
  Learn about the different types of data that pass through the AI and where to
  place it in your application
---

# Types of Data That Pass Through the AI

## Overview

Raw data provides the context for the AI's functionality and how it interacts with the user. In this guide, we'll discuss the different types of data that an AI might collect and where you will want to capture that data when building your MindStudio app.&#x20;

## Types of Data&#x20;

### Global Data&#x20;

Global data refers to data that **hardly ever changes** and is built in to the knowledge base of your AI.&#x20;

This data is captured as the context you provide to your AI in the form of a [prompt](https://docs.youai.ai/youai/getting-started-mindstudio/how-to-write-prompts-in-mindstudio). You can use the prompt to **define the role** of your AI and provide **step by step instructions** on how it should perform.&#x20;

Global data can also include uploaded **data sources** that don't need to be continuously referenced throughout your automation workflow. For example, providing the AI with a data source that includes company information like a mission statement, and brand documentation would be considered global data.&#x20;

**Examples of Global Data:** Company info, brand documents, training materials, and guides.

### Onboarding Data

Onboarding data refers to data that is **consistent** but might need to be edited by your users later on. This data should be captured in the **onboarding flow** of your app, in the form of **user inputs**.&#x20;

It is recommended that onboarding data be [grouped under a single variable](https://docs.youai.ai/youai/variables/how-to-group-inputs-into-a-single-variable) that can be referenced in the prompt or in a **Send Message automation block**.&#x20;

**Examples of Onboarding Data:** Sales team preferences, market trends, and writing samples.

### Runtime Data

Runtime data refers to data that **changes every session** and will need to be filled out each time a new session starts.&#x20;

This data is captured in the **automation flow** of your app via **user inputs** and **data queries**. Runtime data is typically the last piece of raw data passed through the AI before a chat session.

**Examples of Runtime Data:** Customer info, Point of Contact info, and specific data queries.&#x20;

## Conclusion

Knowing where and at which point to provide context and capture user data is an integral part of the app creation process. It ensures that the AI provides your users with the correct outputs and functions efficiently. Remember to always test your AI's and experiment with different flows to find what works best for your use case.&#x20;

