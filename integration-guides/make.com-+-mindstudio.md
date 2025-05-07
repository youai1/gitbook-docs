---
description: Integrate MindStudio AI Agents with Make.com
---

# Make.com + MindStudio

MindStudio Agents can be triggered directly from [Make.com](https://www.make.com/) using the MindStudio app in a Make scenario. This guide walks you through the full setup.

## Prerequisites

Before you start:

* You must have a **MindStudio account** with a published AI Agent.
* You'll need your **Agent ID** and an **API key** from the MindStudio Developer Portal.
* Your agent must have **Launch Variables** setup in the Start Block.
* (optional) Set your Terminator Block to the End behavior

***

### How to find your Agent ID

1. Open the Agent you'd like to call via API
2. In the Editor, click the top folder to open the Agent Settings
3. On the Metadata tab, you'll find the Agent ID at the bottom.
4. Click on the Agent ID to copy it to your clipboard.

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 12.59.51 PM.png" alt=""><figcaption><p>Agent ID in Metadta Tab</p></figcaption></figure>

***

### How to get an API Key

1. Go to [https://app.mindstudio.ai/developer/api-keys](https://app.mindstudio.ai/developer/api-keys)
2. Click on "Create Key"
3. Name your Key
4. Click on the key to copy it to your clipboard

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 1.04.24 PM.png" alt=""><figcaption><p>Create an API Key</p></figcaption></figure>

***

### How to create Launch Variables

1. Open the Agent you'd like to call via API
2. In the automations tab, click on the **Start Block**
3. Make sure your **Run Mode** is set to **On-Demand**
4. At the top of the configuration panel click to add new launch variables

<figure><img src="../.gitbook/assets/Screenshot 2025-05-05 at 1.07.54 PM.png" alt=""><figcaption><p>Creating Launch Variables</p></figcaption></figure>

***

## Step-by-Step Setup in Make

### 1. Add a MindStudio App Module

* Click the "+" button or the wrench icon to add a new module
* Search for "**MindStudio**" in the Apps and Modules list.
* Once added, select the **Run an App** action

***

### 2. Connect Your MindStudio Account

* Name your connection.
* Enter your **`API key`**.  [See section above to get your API key](make.com-+-mindstudio.md#how-to-get-an-api-key)
* Save the connection.

***

### 3. Configuring the MindStudio App Module

* Enter your **`Agent ID`** . [See section above to get your Agent ID](make.com-+-mindstudio.md#how-to-find-your-agent-id)
* Enter your workflow name. (Ex: `Main.flow`)
* Enter your launch variables by clicking "**+ Add Item**". For each variable enter the following:
  1. **`Variable Name`** - The name of the launch variable in your MindStudio workflow. [See section above to learn how to create launch variables](make.com-+-mindstudio.md#how-to-create-launch-variables)
  2. **`Variable Value`** - These values will come from your Make scenario. You can click into the form field to view values from previous steps in the&#x20;
* Click "**Save**" to confirm configurations.

***

### 4. Use the Agent Output&#x20;

* When the agent is run in a Make scenario, use the returned **`result`** value in the modules later in the scenario. This value represents the output of the AI Agent.



## Test & Debug <a href="#test-and-debug" id="test-and-debug"></a>

Run the module manually with sample data from the previous module. If there’s an error, check the debugging tools. You may also consider using n8n's built in assistant to help debug.

#### Common issues: <a href="#common-issues" id="common-issues"></a>

* Invalid API Key → Ensure your key is copied correctly from MindStudio.
* Invalid Agent ID → Only use published Agent IDs.
* Missing variables → Ensure all required launch variables are included.

