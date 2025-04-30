---
description: via Signed Access URLs
---

# Embedding AI Agents

MindStudio allows you to embed your AI Agents seamlessly into your product or website, using **signed access URLs**—without requiring end users to sign up for a MindStudio account.

{% embed url="https://www.youtube.com/embed/ldq-4mX28Ng" %}

## Overview

Signed access URLs provide secure access to a specific AI Agent for a specific user. These are particularly useful if you already manage your own user accounts and want to embed an agent without forcing additional authentication steps.

* URLs expirations can be set (1 hour to infinite)
* You can generate **unlimited URLs**
* Old URLs **do not expire** when new ones are generated

## How It Works

1. Your backend requests a signed access URL from the MindStudio API.
2. You optionally include your internal user ID (for run history tracking).
3. MindStudio responds with a signed URL.
4. You serve this URL to your user—via redirect or iframe.

If a `userId` is provided, run history for that user will be consistent across sessions. Otherwise, a new temporary user will be created each time.

## Getting the Signed URL

#### Curl Example

```bash
curl -X POST https://api.mindstudio.ai/developer/v2/generate-signed-access-url \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "agentId": "AGENT_ID",
    "userId": "your-external-user-id"
  }'
```

#### JavaScript (Fetch) Example

```js
const response = await fetch('https://api.mindstudio.ai/developer/v2/generate-signed-access-url', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    agentId: 'AGENT_ID',
    userId: 'your-external-user-id',
  }),
});

const { url } = await response.json();
// Use the URL in an iframe or redirect
```

### Example Flow

Here’s how you can integrate it into your product:

1. **User logs in** to your app.
2. **Frontend** loads a secure route (e.g., `/tools/my-agent`).
3. **Frontend calls your backend**, which:
   * Verifies the user’s session
   * Calls MindStudio’s `generate-signed-access-url` endpoint
4. **Your backend returns** the URL to the frontend.
5.  **Frontend embeds** the agent in an `<iframe>`:

    {% code overflow="wrap" %}
    ```html
    <iframe src="https://app.mindstudio.ai/signed-access/abc123..." width="100%" height="800px"></iframe>
    ```
    {% endcode %}

    Or, you can redirect the user to the URL directly.

### Best Practices

* **Always** generate a new signed URL per session.
* **Never expose your API key** in client-side code.

***

## Getting Signed URLs Using Make.com

### Prerequisites

* A Make.com account
* Your MindStudio **API key**
* Your Agent’s **ID**
* A backend HTTP module or webhook trigger (to retrieve or forward the signed URL)
* Optional: A source for the user ID (e.g., webhook, form, database)

### Step-by-Step with Make:

1. **Create a Scenario:** Start with a Webhook trigger from your frontend
2. **Add HTTP Module:** Use the **HTTP → Make a Request** module.
3.  **Configure the HTTP POST:**

    * **URL:** `https://api.mindstudio.ai/developer/v2/generate-signed-access-url`
    * **Method:** `POST`
    *   **Headers:**

        | Key           | Value                 |
        | ------------- | --------------------- |
        | Authorization | `Bearer YOUR_API_KEY` |



    * **Content-Type:** `JSON (application/json)`
    * **Body Type:** `Raw`
    *   **Request content:**

        ```json
        {
          "agentId": "YOUR_AGENT_ID",
          "userId": "{{your_user_id_variable}}"
        }
        ```
    * **Parse the Response:** `Yes`
      * You'll need to extract the `url` field from the API response.
4. **Use the Signed URL in the frontend iframe code.**&#x20;

***

## Getting Signed URLs Using Zapier

### Prerequisites

* Zapier account
* A MindStudio API key and Agent ID
* Zapier Webhooks by Zapier (Premium trigger/action)
* Optional: A source for the user ID (e.g., webhook, form, database)

### Step-by-Step with Zapier:

1. **Create a Zap:**  Start with a Webhook trigger from your frontend
2. **Add Webhooks by Zapier – POST Request**
   * **URL:** `https://api.mindstudio.ai/developer/v2/generate-signed-access-url`
   * **Payload Type:** `JSON`
   *   **Data:**

       | Key     | Value                  |
       | ------- | ---------------------- |
       | agentId | `YOUR_AGENT_ID`        |
       | userId  | `user_id_from_trigger` |
   *   **Headers:**

       | Key           | Value                 |
       | ------------- | --------------------- |
       | Authorization | `Bearer YOUR_API_KEY` |
       | Content-Type  | `application/json`    |


3. **Extract the URL:** Use the `url` from the webhook response in subsequent steps.
4. **Use the Signed URL in the frontend iframe code.**&#x20;

***

## Getting Signed URLs Using n8n

### Prerequisites

* An active **n8n instance**
* Your **MindStudio API Key**
* The **Agent ID** you want to embed
* Optional: A source for the user ID (e.g., webhook, form, database)

### Step-by-Step with n8n:

1. Start with a Webhook trigger from your frontend
2. Add an HTTP Request Node
   * **HTTP Method:** `POST`
   * **URL:** `https://api.mindstudio.ai/developer/v2/generate-signed-access-url`

* **Authentication:** `None (manual headers)`
*   **Headers:**

    | Key           | Value                 |
    | ------------- | --------------------- |
    | Authorization | `Bearer YOUR_API_KEY` |
    | Content-Type  | `application/json`    |
* **Body Content Type:** `JSON`
* **JSON Parameters:** `Enabled`
*   **Body Parameters:**

    ```json
    {
      "agentId": "YOUR_AGENT_ID",
      "userId": "={{$json.userId}}"
    }
    ```

You can replace `{{$json.userId}}` with however you're passing in or storing user identifiers.

3. **Extract the URL:** After the HTTP node runs, you’ll get a response that includes a `url` field.
4. **Use the Signed URL in the frontend iframe code.**&#x20;

