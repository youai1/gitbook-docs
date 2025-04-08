---
description: Send a message to a specified Slack channel in a MindStudio workflow
---

# Post to Slack

## Configuration&#x20;

### Account&#x20;

#### Dynamic (Ask at runtime)

This setting will ask a user to login to their Slack account when they run the app.

#### Connect a New Account

Follow the instructions on the pop-up window to directly connect MindStudio to your Slack account.&#x20;

### Message Type&#x20;

Select the message type you want to send to Slack. Options include:

* **Markdown Text**
* **Slack Block Kit Blocks**

### Channel

Select the Slack channel you want to send your message to.&#x20;

### Message Content&#x20;

Enter the message you want to send to Slack. This section can include variables.&#x20;

If you are using the **Slack Block Kit Blocks** message type, the content area will automatically fill with the correct JSON structure.&#x20;

**Example:**&#x20;

{% code overflow="wrap" fullWidth="false" %}
```json
[
	{
		"type": "section",
		"text": {
			"type": "mrkdwn",
			"text": "This is a mrkdwn section block :ghost: *this is bold*, and ~this is crossed out~, and <https://google.com|this is a link>"
		}
	}
]
```
{% endcode %}



## Sample Output

```json
No output.
```
