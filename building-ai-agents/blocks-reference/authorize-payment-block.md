---
description: Authorize a user to pay to use your AI agent.
---

# Authorize Payment Block

The Authorize Payment block allows a user to authorize to pay you to use your AI agent. The user is presented with this block each time they run your AI agent. The user must have a MindStudio account.

## Configuration

### Amount&#x20;

Specify the per-unit amount the user must authorize payment. The user will be charged the full amount when a [Capture Payment](capture-payment-block.md) block captures payment.

### Quantity

Specify the number of units to authorize. By default is **1**.

{% hint style="info" %}
This setting may include variables.
{% endhint %}

### Statement Description

Describe the charge for the user.

### On Reject

Select the block to route to if the user rejects the payment authorization.

<div data-full-width="true"><figure><img src="../../.gitbook/assets/Screenshot 2026-03-06 at 11.08.49 AM.png" alt=""><figcaption></figcaption></figure></div>
