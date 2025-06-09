---
description: Route block paths based on AI decision making
---

# Logic Block

{% embed url="https://youtu.be/XV3eopnYINM" %}

The **Logic Block** uses AI to dynamically decide which route to take based on the most likely condition. Unlike the **Menu Block**, where users make the choice, the **Logic Block** evaluates predefined conditions and autonomously selects the appropriate path. This is ideal for automating decisions without direct user input.

## **Configurations**

### **Conditions**

Define the conditions the AI will evaluate to determine the most likely path. Each condition corresponds to a case that the workflow can route to.

#### **Add a Condition**:

Use the **+ Add Condition** button to define multiple cases. Each condition should describe a unique scenario the AI can evaluate. Conditions should incorporate variables to make routing dynamic and context-aware.

**Example 1: Customer Sentiment**

* **Case #1**: `The customer is satisfied with the service based on the following interaction:`` `<mark style="color:red;">`{{message_transcript}}`</mark>
* **Case #2**: "The customer is requesting support based on the following interaction: <mark style="color:red;">`{{message_transcript}}`</mark>"

**Example 2: Order Status**

* **Case #1**: <mark style="color:red;">`{{order_status}}`</mark>` ``== "complete"`
* **Case #2**: <mark style="color:red;">`{{order_status}}`</mark>` ``== "incomplete"`

#### **Set a Destination**:

For each condition, click the **Select Destination** button and choose a block on the canvas where the Logic Block should route if that condition is selected. Once connected, the circle next to the destination button will fill in, confirming the route.

### **Evaluation Settings**

Configure how the AI evaluates the conditions.

### **Engine**

The Logic Block uses AI engines to evaluate conditions and make routing decisions. Choose an engine based on your workflow's complexity and precision requirements:

* **Default Engine**
  * Reliable and general-purpose engine for most use cases.
  * Optimized for simple workflows requiring consistent and predictable decisions.
* **Experimental Engine**
  * Suitable for advanced use cases exploring cutting-edge capabilities.
  * May include beta features, offering innovative decision-making strategies.
  * Recommended for testing new workflows or unconventional logic setups.
* **Haiku Engine**
  * Low cost, low latency engine for quick decision making
  * May not be as accurate as other engines

***

## **How It Works**

1. The Logic Block presents multiple conditions to the AI engine.
2. Based on the input and context, the AI evaluates the conditions and determines the most likely match.
3. The Logic Block routes the workflow to the destination associated with the selected condition.

***

## Best Practices

* **Clearly Define Conditions**: Use specific and distinct criteria for each case to avoid overlaps.
* **Test Scenarios**: Simulate workflows to ensure the AI selects the expected routes.
* **Use Variables**: Incorporate variables in conditions to dynamically adjust the decision-making process.
