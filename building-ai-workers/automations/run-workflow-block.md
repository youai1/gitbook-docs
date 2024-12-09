---
description: Execute a sub-workflow within a parent workflow
---

# Run Workflow Block

The **Run Workflow Block** allows you to execute a separate workflow within your main workflow. This block is ideal for running sub-processes and reusing common processes across multiple workflows.

***

## **Configurations**

### **App**

Select the AI Worker containing the workflow you want to run.

* Use the dropdown to choose the appropriate AI Worker.
* Ensure the selected AI Worker contains the workflow you want to execute.

### **Workflow**

Choose the specific workflow within the selected AI Worker to execute.

* Select from available workflows in the chosen AI Worker.
* For modular workflows, ensure the selected workflow is designed for integration.

### **Launch Variables**

Define the values to pass to the required variables in the selected workflow.

* Assign static values or use variables from the current workflow.

#### Example:

* Variable: <mark style="color:red;">`customer_name`</mark>
* Value: <mark style="color:red;">`{{userName}}`</mark>

### **Output Variables**

Map the outputs of the sub-workflow back to variables in the parent workflow.

* Assign the <mark style="color:red;">`variable_name`</mark> you want to store the sub-workflow's output in.
* Enter the <mark style="color:red;">`variable_name`</mark> without curly braces.

#### Example:

* Variable: <mark style="color:red;">`customer_profile`</mark>
* Mapped to: <mark style="color:red;">`customer_info`</mark> in the parent workflow

***

## **Preparing the Sub-Workflow**

Before a sub-workflow can be used in the **Run Workflow Block**, it must be configured with:

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
