---
description: Execute a sub-workflow within a parent workflow
---

# Run Workflow Block

{% hint style="danger" %}
**REQUIRED:** Before a sub-workflow can be used in the Run Workflow Block, the **sub-workflow** must be configured with:&#x20;

* **Launch Variables** in the **Start Block**&#x20;
* **Structured JSON Outputs** in the **End Block.**

***

If these are not configured, then the workflow will not run properly.
{% endhint %}

The **Run Workflow Block** allows you to execute a separate **sub-workflow** within your main workflow. This block is ideal for running sub-processes and reusing common processes across multiple workflows.

{% embed url="https://youtu.be/6GubegBVSXA" %}

***

## **Configurations**

The Run Workflow block allows you to execute a separate sub-workflow from within the current workflow. It’s ideal for reusing logic, modularizing large flows, or performing iterative processing with dynamic inputs.

To function properly, the selected sub-workflow must be configured with:

* **Launch Variables** in the Start Block
* **Structured JSON Outputs** in the Terminator Block

If these are not present, the workflow will fail to execute.

***

### Agent

Select the AI Agent that contains the workflow you want to run. Use the dropdown to choose from your available agents.

### Workflow

Choose the specific sub-workflow from the selected agent. Only workflows that include Launch Variables and JSON Outputs will appear here.

***

### Parameters

#### Launch Variables

Assign values to the sub-workflow’s input variables. These can be static or dynamic using

`{{variables}}`.

**Example:**

* `customer_name` → `{{userName}}`
* `order_id` → `12345`

#### Output Variables

Map the structured outputs returned from the sub-workflow into variables in the parent workflow.

**Example:**

* `customer_profile` → `customer_info`

***

### Iteration Settings

Use this section to run the selected workflow multiple times — once for each item in an input list.

#### Iterator

Choose how items are extracted for iteration:

* **Auto-Extract (Default):** Uses the Extraction Prompt to pull items from unstructured input.
* **String Array:** Treats the input as a delimited string (e.g., comma-separated list).
* **JSON Array Input (Advanced):** Expects a valid JSON array; each item becomes a separate run.

***

#### Input Data / Input Array

Specify the input variable that contains the array or string to iterate through.\
For example: `{{user_email_list}}`

***

#### Extraction Prompt _(only for Auto-Extract)_

Provide an instruction for the thing you'd like to pull from the input variable. Each extracted item is stored as a variable called `{{item}}`.

**Ex:** `Extract all emails`

**Output:** The variable `{{item}}` is the email that is extracted

***

#### Item Separator _(only for String Array)_

Choose how to split the input string:

* Comma
* Semicolon
* Pipe
* Custom

**Ex:** If the input string is  `Dog, Cat, Fish` , then select the `Comma` option

***

#### Output Variable

The result of each sub-workflow run is stored in a JSON array at this variable name.

**Example:**

`batch_results`

***

#### Execution Mode

Choose how runs are processed:

* **Parallel:** Runs all iterations in batches (faster)
* **Sequential:** Runs one at a time (slower)

***

#### Error Behavior

Set how the workflow should respond to errors:

* **Fail:** Stop all runs on first error
* **Ignore Failed Runs:** Skip failed items and continue

***

#### Retry Attempts

Define how many times to retry failed runs. Use cautiously to avoid unintended costs.

***

## **Preparing the Sub-Workflow**

### **Launch Variables**:

Define the launch variables that the parent workflow will provide. Go to the sub-workflow you'd like to run and add Launch Variables in the **Start Block** of the sub-workflow.

![Define Launch Variables in Sub-workflow](<../../.gitbook/assets/Screenshot 2024-12-04 at 9.53.58 PM.png>)

#### Example Launch Variables:

* <mark style="color:red;">`customer_name`</mark>: The parent workflow will pass the customer name down to the sub-workflow.
* <mark style="color:red;">`order_id`</mark>: The parent workflow will pass the ID of the customer's order down to the sub-workflow.

### **Structured Outputs**:

Define the **Return Data** that the sub-workflow will return to the parent workflow. Add these variables to the sub-workflow’s **Terminator Block** under **Return Data -> JSON Output**.

![Define Return Data in Sub-workflow](<../../.gitbook/assets/Screenshot 2024-12-04 at 9.56.44 PM.png>)

#### Example Return Data:

* <mark style="color:red;">`customer_profile`</mark>: Returns customer details retrieved from the sub-workflow.
* <mark style="color:red;">`order_status`</mark>: Returns the status of the processed order from the sub-workflow.

**Note:** If a workflow lacks these configurations, you will see an error message:

> _**"The selected workflow has not been configured with launch variables and structured outputs."**_

***

## Best Practices

* **Ensure Variable Alignment**: Make sure that required variables in the sub-workflow are properly assigned with values during execution.
* **Optimize Your Workflows**: Use this block to simplify complex workflows by breaking them into manageable, reusable components.
* **Test Input and Output Mapping**: Verify that all variables are passed correctly between the parent and sub-workflows.
* **Maximum Iterations Limit**: By default, agents can perform 100 actions before stopping automatically. This limit is to protect you from uncontrolled loops, runaway costs, and other unintended effects. If you need to process more than 100 actions per request, you can increase this limit on a per-agent basis by modifying the "Maximum Invocations per Operation" setting in the Agent's "Runtime" settings screen (click the Agent's name in the left-side Navigator to open the Settings pane, then find "Runtime" under the "Advanced" heading).
