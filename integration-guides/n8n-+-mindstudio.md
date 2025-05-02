---
description: Integrate MindStudio AI Agents with n8n
---

# n8n + MindStudio

MindStudio Agents can be triggered directly from [n8n](https://n8n.io/) using an HTTP Request node to run custom workflows. This guide walks you through the full setup.

## Prerequisites

Before you start:

* You must have a **MindStudio account** with a published AI Agent.
* You'll need your **Agent ID** and an **API key** from the MindStudio Developer Portal.
* Your agent must have **Launch Variables** setup in the Start Block.

### How to find your Agent ID

1. Open the Agent you'd like to call via API
2. In the Editor, click the top folder to open the Agent Settings
3. On the Metadata tab, you'll find the Agent ID at the bottom.
4. Click on the Agent ID to copy it to your clipboard.

### How to get an API Key

1. Go to [https://app.mindstudio.ai/developer/api-keys](https://app.mindstudio.ai/developer/api-keys)
2. Click on "Create Key"
3. Name your Key
4. Click on the key to copy it to your clipboard

### How to create Launch Variables

1. Open the Agent you'd like to call via API
2. In the automations tab, click on the **Start Block**
3. Make sure your **Run Mode** is set to **On-Demand**
4. At the top of the configuration panel click to add new launch variables

## Step-by-Step Setup in n8n

#### 1. **Add an HTTP Request Node**

* Click the “+” button in n8n
* Search for and select **HTTP Request**

#### 2. **Configure HTTP Request Details**

Under the HTTP Request Node:

* **HTTP Method**: `POST`
* **URL**: `https://v1.mindstudio-api.com/developer/v2/agents/run`
* **Authentication**: Set to "None"
* **Headers**:
  * Key: `Authorization` — Value: `Bearer YOUR_API_KEY`

#### 3. **Add Body**

* Set the **Body Content Type** to `RAW`&#x20;
* Set **Content Type** to `application/json`
* Paste your payload into the body field, like this:

<pre class="language-json"><code class="lang-json">{{
{
workerId: 'AGENT_ID',
variables: {
<strong>    variableName1: "value1",
</strong>    variableName2: "vallue2",
},
workflow: 'NAME_OF_YOUR_WORKFLOW.flow'
}
}}
</code></pre>

> You can use **expressions** (`$json["fieldName"]`) to dynamically populate these variables from previous n8n nodes. Or use the n8n interface to click and drag values in from previous steps.

***

## Test & Debug

Run the workflow manually with sample data. If there’s an error, check the `HTTP Response Code` and `body` message. You may also consider using n8n's built in assistant to help debug.

### Common issues:

* Invalid API Key → Ensure your key is copied correctly from MindStudio.
* Invalid Agent ID → Only use published Agent IDs.
* Missing variables → Ensure all required launch variables are included.

