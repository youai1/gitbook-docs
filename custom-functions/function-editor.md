---
description: Learn how to use the Function Editor.
---

# Function Editor

## Overview

Build [Custom Functions](what-is-a-custom-function.md) in Function Editor. The Function Editor has three components.

* [Code tab](function-editor.md#code-tab)
* [Configuration tab](function-editor.md#configuration-tab)
* [Test Data tab](function-editor.md#test-data-tab)

## Code Tab

In the **Code** tab of the Function Editor, enter the JavaScript code to run your Custom Function in an [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md). You can also edit the code of pre-built Custom Functions when you import them in your Workflow.

### Best Practices to Coding a Custom Function in the Code Tab

* Plan how you want your Custom Function to work with the third-party service or application with which it will interact:
* Plan requirements for your Custom Function.
* Consider if the AI Developer requires an account or subscription with the service to use your Custom Function.
  * Plan which permissions, if any, the AI Developer must have with the service to use your Custom Function.
  * Plan what interactions your Custom Function makes with the service.
* Use commenting in your JavaScript code for other AI Developers to better understand how you built your Custom Function.

## Configuration Tab

In the **Configuration** tab of the Function Editor, define a user interface that AI Developers enter configuration settings when they use your Custom Function in their AIs.

### Best Practices to Coding in the Configuration Tab

* Set the Block style to make your [Run Function Blocks](../automation-workflows/types-of-automation-blocks/#run-function-block) easily recognizable within the Automation Canvas.
* Document requirements in the Custom Function configuration so AI Developers plan for them prior to configuring your Custom Function in their AIs.
* Build the configuration settings for your Custom Function to be easily understandable to novice and experienced AI Developers. This increases adoption of your Custom Function in the MindStudio community.

## Test Data Tab

In the **Test Data** tab of the Function Editor, test your Custom Function.

1. Select the **Test Data** tab.
2. Enter test data.
3. Select the **Run Function** icon.
4. View the console response to the right of the **Test Data** tab to ensure it runs as expected.

### Best Practices to Coding in the Test Data Tab

* Optimize the JavaScript code in your Custom Function.
* Include the following prior to running your Custom Function:
  * Include any API keys, tokens, or webhook URLs as required by that Custom Function.
  * Include sample data, such as `Hello`, to ensure data successfully sends to the connecting service.&#x20;
* Verify that the service connected to your Custom Function receives the sample data.
* Test often.
