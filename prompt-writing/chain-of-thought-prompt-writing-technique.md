---
description: >-
  Use Chain-of-Thought (CoT) prompt writing technique as an advanced method to
  write Prompts.
---

# Chain-of-Thought Prompt Writing Technique

## Overview

Chain-of-Thought (CoT) prompting technique enhances the reasoning capabilities of AI models by guiding them to explain their reasoning process step by step. This method works well for complex tasks that require a series of logical steps to reach a conclusion.

CoT prompting encourages AI models to break down their thought process into intermediate steps, making the reasoning more transparent and easier to follow. Achieve this by providing examples that outline the reasoning process, which the AI model then emulates when answering similar [Prompts](what-is-a-prompt.md). This technique can be helpful when instructing the AI model to perform arithmetic, commonsense, and symbolic reasoning. CoT prompting technique not only enhances the accuracy of responses but also provides insights into how your selected AI model approaches problem-solving. Not all AI models perform problem solving equally well.

Automated CoT (A-CoT) automates the CoT technique.

## Guidelines for Chain-of-Thought Prompting Technique

* **Require the AI model to think step-by-step:** Explicitly state for the AI model to "think step-by-step" in your Prompt. This indicates to the AI model to break down its reasoning into a structured response. Explicitly state for the AI model to articulate each step of its thought process, leading logically from one step to the next until it reaches a conclusion.
* **Provide a specific problem statement:** State the problem or question that you expect the AI model to solve. Ensure that your problem statement is well-defined, concise, and grammatically correct.
* **Provide examples:** Provide several examples where the reasoning process is explicitly outlined. Place your examples into an Examples section using [Markdown](what-is-markdown.md) as described in [Prompt writing best practices](best-practices-for-writing-prompts.md). This helps the model understand the desired format and approach for the reasoning process.
* **Test your CoT Prompt and iterate to improve it:** Test your CoT Prompt in [Prompt Tester](test-your-prompt.md) with different configurations. Refine your Prompt based on the outcomes. Pay attention to how well the AI model follows the reasoning steps and adjust your Prompt accordingly. The steps the AI model outlines should be accurate, relevant to the problem you are solving, and contribute to solving that problem.

## Example of a Prompt Using Automated Chain-of-Thought Prompting Technique

{% code overflow="wrap" %}
```
# Inventory Management Forecasting App


## Purpose

- The Assistant is an inventory management forecasting app.
- The app forecasts inventory levels for the upcoming quarter that is provided by the Human.
- The app optimizes inventory levels based on sales data, current inventory levels, and anticipated market trends.
- The Human provides the sales data, current inventory levels, and anticipated market trends.


## Example

Refer to the following example of how inventory level forecasting was performed last quarter.
- Product A had a sales volume of 1,000 units. The current inventory level is 200 units. There is an anticipated market trend indicating a 10% increase in demand.
- Expected demand was calculated for the next quarter and adjusted inventory levels as follows:

1. **Calculate expected demand:** Start with the sales volume of the last quarter for Product A, which is 1,000 units. Anticipating a 10% increase in demand, the expected demand for the next quarter would be 1,100 units.
2. **Adjust inventory levels:** Considering the current inventory level of 200 units, to meet the expected demand of 1,100 units, 900 more units were ordered for Product A for the next quarter.


## Goal

- The app's goal is to minimize overstock and understock situations to maximize profitability.


## Output

- Explicitly state the step-by-step reasoning into a structured response.
- Output the response into a table with column headers "Previous Inventory", "Anticipated Growth", and "Inventory Forecasting", in that order.
- Enter your step-by-step reasoning into the "Inventory Forecasting" column.
```
{% endcode %}
