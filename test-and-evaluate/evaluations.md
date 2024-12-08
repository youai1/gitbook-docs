# Evaluations

MindStudio's **Evaluations** feature enables you to rigorously test the accuracy and consistency of your workflows. By creating structured tests, you can validate expected outcomes, identify areas for improvement, and ensure your workflows are functioning as intended.

***

## Requirements

To use the Evaluations tool effectively, your workflow must meet the following requirements:

* **Launch Variables**: The workflow should be configured with launch variables to define inputs.
* **End Block**: The workflow must contain an End block to return outputs.

***

## Steps to Evaluate a Workflow

### 1. Create Evaluation(s)

Evaluations are structured test cases you can create to validate your workflow's output. There are two main ways to create evaluations:

#### **Manually**:

Define each test case from scratch by specifying the input variables and expected results. This approach gives you complete control over each evaluation.

#### **Using the Generate Button**:

Click **Generate** button to automatically populate evaluation cases using default or existing input data. Choose the number of test cases and optionally give the generator additional context about the test cases you want generated.

![Test Case Generator](<../.gitbook/assets/Screenshot 2024-12-06 at 5.13.26 PM.png>)

### 2. Run the Evaluations

Once you've created your evaluations, you can run them all at once or individually to test your workflow's output against the defined expectations.

#### Run all test cases at once

Click **Run all** at the top left to run all of the test cases at the same time. Results may take more time to appear depending on the size of the workflow and how many test cases you created.

#### Run an individual test case

Hover over the left side of the test case row and click on the **Play icon** to run an individual test case. Ideal if you don’t want to rerun previous tests.

***

## Anatomy of an Evaluation

Each evaluation consists of three main components:

#### **Input**

The set of variables or data points that the workflow will process.

#### **Expected Result**

The anticipated output for the given input. This can be configured for:

* **Literal Match**: The output must exactly match the expected result.
* **Fuzzy Match**: The output can vary slightly and still be considered correct if it meets specified criteria.

#### **Result**

The actual output produced by the workflow, displayed alongside the expected result for comparison.

***

## Exporting Evaluations to CSV

Evaluations can be exported to a CSV file by clicking on the **Export button** at the bottom right, sharing, or further analysis. The export includes all input, expected results, and actual results, making it easy to communicate Evaluations to team members or stakeholders.

***

## Usage Example: Content Moderation

In this example, we'll validate the accuracy of a **Content Moderation** workflow that classifies user-generated content. Each evaluation tests the workflow's ability to label inputs accurately:

![](<../.gitbook/assets/Screenshot 2024-12-06 at 5.12.17 PM.png>)

* **Input**: A piece of text or content submitted for moderation, such as:
  * `"This review is just copied from another site. Plagiarism!"`
  * `"I hate this product and the company that makes it. They are the worst!"`
* **Expected Result**: The anticipated classification for each input, such as:
  * `Plagiarism or Copyright Violation`
  * `Hate Speech or Offensive Content`
* **Result**: The actual classification provided by the workflow.

Evaluations will indicate whether the workflow correctly classifies content into categories such as "Clear," "Spam or Promotional Content," or "False or Misleading Information."

For example, the workflow should identify

> `"I hate this product and the company that makes it. They are the worst!"`

as `Hate Speech or Offensive Content`.
