---
description: >-
  Build a MindStudio AI that automatically fetches availability to schedule a
  meeting on Calendly.
---

# Calendly Fetch Availability: Custom Function

## What is Calendly?

[Calendly](https://calendly.com/) provides cloud-based automated services to schedule, prepare, and follow up on external meetings.

## What Can I Do With MindStudio and Calendly?

Build a MindStudio AI that automatically fetches availability to schedule a meeting on Calendly.

## What is Required for This Custom Function?

* Calendly Professional account.
* Calendly API token. See [Get Calendly API Token](calendly-fetch-availability-custom-function.md#get-calendly-api-token).
* **Calendly: Fetch Availability** Custom Function.

## Get Calendly API Token

1. Login to your Calendly account.
2. Navigate to the **Integrations & apps** page.
3. Select the **API & connectors** category.
4. Select the **API & webhooks** card.
5. Locate the **Personal access tokens** card.
6. Select the **Get a token now** link.
7. Select the **Continue** button.
8. Name your personal token, and then select the **Create token** button.
9. Store the personal token in the [**Calendly Personal Token** setting](calendly-fetch-availability-custom-function.md#calendly-personal-token) in MindStudio’s Calendly Fetch Availability Custom Function.

## Configuration

### Calendly Personal Token

Enter your Calendly personal token.

### Availability Output Variable

Enter the full availability the user has in Calendly. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores availability the user has provided in a User Input. **Example:**

```
{{Availability}}
```

### Events Output Variable

Enter the events the user already has in Calendly. Optionally, reference a Variable that stores events the currently scheduled events that the user has provided in a User Input. **Example:**

```
{{Events}}
```

### Scheduling Link Output Variable

Enter the output Variable that stores the user the link to schedule an event on Calendly. Note to not use double curly braces when entering the Variable name into the Scheduling Link Output Variable setting. **Example:**

```
Link
```
