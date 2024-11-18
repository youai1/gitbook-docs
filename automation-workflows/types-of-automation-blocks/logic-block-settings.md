---
description: Configure these settings for the Logic Block.
---

# Logic Block Settings

## Add a Condition to a Logic Block

Select the **Add Condition** button.

## Set the Condition the Logic Block Evaluates

1. [Add a condition](logic-block-settings.md#add-a-condition-to-a-logic-block).
2. Enter the condition using natural language that the Logic Block evaluates. Optionally, reference [Variables](../../user-inputs-and-variables/what-is-a-variable.md) in the condition using double curly braces around the Variable name. See notes below.

### Best Practices to Write Conditions for the Logic Block

#### Enter Conditions as the Action or Decision to Make

Enter conditions using natural language as the action or decision you want the AI to make. Avoid using personal pronouns such as I or You.

**Bad Example**

```
I want the {{lead}} to be valuable.
```

**Good Example**

```
The {{lead}} is valuable based on the following: {{context}}
```

#### Use Quotation Marks Around Text Strings to Evaluate

When evaluating text strings or the values of referenced Variables, place that text string in quotation marks.

**Good Example**

```
The "{{lead}}" is not valuable based on the following: {{context}}
```

## Remove a Condition from a Logic Block

Select the (**-**) icon inside the condition to remove.

## Set to Which Block the Logic Block Routes Workflow

1. Select the circle below the condition to dynamically set routing.
2. In the [Automation Workflow](../what-is-an-automation-workflow.md), select to which Block the Workflow routes when its condition is true.

A connection sets from the Logic Block to the selected Block.
