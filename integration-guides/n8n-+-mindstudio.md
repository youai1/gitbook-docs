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

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 12.59.51 PM.png" alt=""><figcaption><p>Agent ID in Metadta Tab</p></figcaption></figure>

### How to get an API Key

1. Go to [https://app.mindstudio.ai/developer/api-keys](https://app.mindstudio.ai/developer/api-keys)
2. Click on "Create Key"
3. Name your Key
4. Click on the key to copy it to your clipboard

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 1.04.24 PM.png" alt=""><figcaption><p>Create an API Key</p></figcaption></figure>

### How to create Launch Variables

1. Open the Agent you'd like to call via API
2. In the automations tab, click on the **Start Block**
3. Make sure your **Run Mode** is set to **On-Demand**
4. At the top of the configuration panel click to add new launch variables

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 1.07.54 PM.png" alt=""><figcaption><p>Creating Launch Variables</p></figcaption></figure>

## Step-by-Step Setup in n8n

#### 1. **Add an HTTP Request Node**

* Click the “+” button in n8n
* Search for and select **HTTP Request**
* Double-click on the node to open configuration settings

#### 2. Click on Import cURL button at the top right of the&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 3.00.41 PM.png" alt=""><figcaption><p>Import cURL Button</p></figcaption></figure>

#### **3. Paste in this cURL command**

Make sure to change **`YOUR_API_KEY`** - [See section above get your API key](n8n-+-mindstudio.md#how-to-get-an-api-key)

```bash
curl -X POST https://v1.mindstudio-api.com/developer/v2/agents/run \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{}'
  
```

#### 5. Click on `IMPORT`

#### 6. Once imported, change the `Specify Body` setting to&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 3.24.03 PM.png" alt=""><figcaption><p>Send Body Section</p></figcaption></figure>

#### 7. Paste the following code into the `JSON` area

```json
{
    "workerId": "YOUR_AGENT_ID",
    "variables": {
      "LAUNCH_VARAIBLE_1": "VALUE_1",
      "LAUNCH_VARAIBLE_2": "VALUE_2",
    },
    "workflow": "YOUR_WORKFLOW_NAME.flow"
  }
```

#### 8. In the `JSON`, change the following to use your own data:

* **`YOUR_AGENT_ID`** - [See section above to get your AGENT ID](n8n-+-mindstudio.md#how-to-find-your-agent-id)
* **`LAUNCH_VARIABLES`** - [See section above to learn how to create launch variables](n8n-+-mindstudio.md#how-to-create-launch-variables)
* **`VALUES`** - These values will come from your n8n instance. You can clack and drag any on an `INPUT`  into the JSON area to bring it into your code.
* **`YOUR_WORKFLOW_NAME`** - The name of the workflow you want to trigger (Ex: `Main.flow`)

***

## Test & Debug

Run the workflow manually with sample data. If there’s an error, check the `HTTP Response Code` and `body` message. You may also consider using n8n's built in assistant to help debug.

### Common issues:

* Invalid API Key → Ensure your key is copied correctly from MindStudio.
* Invalid Agent ID → Only use published Agent IDs.
* Missing variables → Ensure all required launch variables are included.

