# Debugger

The **Debugger** is a critical tool in MindStudio for testing, troubleshooting, and optimizing workflows. It allows users to examine the execution of their workflows step-by-step, identify issues, and ensure that the expected results are achieved. This tool is especially valuable for understanding the flow of variables, analyzing billing events, and testing how various blocks interact within the workflow.

<figure><img src="../.gitbook/assets/Debugger main (1).png" alt=""><figcaption></figcaption></figure>

## How to Use the Debugger

### 1. Access the Debugger

Open the desired workflow in MindStudio. Switch to the **Debugger** tab from the workflow interface.

You can also open the debugger from an already run workflow by opening the **3 dot menu** and selecting **Show Debugger**.

<figure><img src="../.gitbook/assets/Debugger locate.png" alt=""><figcaption></figcaption></figure>

### 2. Run the Workflow

Use test inputs or variables to trigger the workflow. The workflow execution will be logged in real time. You can run the workflow in many different ways outlined below.

<figure><img src="../.gitbook/assets/Run in debugger.png" alt=""><figcaption></figcaption></figure>

### 3. Analyze Logs

Review the action logs to verify the workflow behaves as expected. Check the **Billing Events** section to ensure cost efficiency. Observe the **Runtime Variables** panel to confirm variable values are correctly updated at each step.

<figure><img src="../.gitbook/assets/runtime Var.png" alt=""><figcaption></figcaption></figure>

### 4. Troubleshoot Errors

Identify blocks with errors or unexpected behavior. Adjust inputs, fix errors, and re-run the workflow to validate changes.

<figure><img src="../.gitbook/assets/errors.png" alt=""><figcaption></figcaption></figure>

### (Optional) Export Logs

Use the **Export** button to download debugging data for documentation or collaborative troubleshooting.

## How to Run & Test Workflows

There are several ways to run and test workflows in MindStudio's debugger, each suited for different testing scenarios and debugging needs. The debugger provides flexible execution options that let you validate your workflow's functionality, from testing the entire flow to focusing on specific components.

**Follow these steps to test a workflow:**

### **Select Run Type**

Click the **Preview** button at the top right corner of the screen to open the preview menu. There are 3 options depending on the block(s) you have selected:

* **Run in debugger:** Executes the entire workflow from start to finish in the debugger.

<figure><img src="../.gitbook/assets/Run in debugger 2.png" alt=""><figcaption></figcaption></figure>

* **Start from selection:** Executes the workflow starting at the selected step (block), skipping all preceding steps.

<figure><img src="../.gitbook/assets/Start from Selection.png" alt=""><figcaption></figcaption></figure>

* **Run Selection:** Executes only the selected portion of the workflow, limited to one or more connected blocks.

<figure><img src="../.gitbook/assets/run from step.png" alt=""><figcaption></figcaption></figure>

**Note:** You can select one or multiple blocks by clicking and dragging to create a selection box around them, or by holding Shift while clicking individual blocks. This selection will define the scope of your test execution.

### **Input Variable Information**

Enter the necessary variable data into the provided input fields within the modal. This information is required for the workflow's execution.

<figure><img src="../.gitbook/assets/Debugger run agent.png" alt=""><figcaption></figcaption></figure>

### **Run the Selection**

After entering the variable data, click the **Run** button at the bottom of the modal. This will execute the workflow starting from the selected block.

### **View Run Logs**

Once the test starts, the **Run Log** for the selected portion of the workflow will appear at the bottom of the **Automations** tab. Outputs generated during the test are automatically stored in the debugger, and these logs are accessible from the main **Debugger** panel, where all execution logs are stored for reference.

<figure><img src="../.gitbook/assets/Run Logs.png" alt=""><figcaption></figcaption></figure>

## Anatomy of Debugger

The Debugger interface is organized into distinct sections that work together to provide comprehensive insights into workflow execution. Each component serves a specific purpose in helping users monitor, analyze, and troubleshoot their workflows effectively.

### Debugger Panel (Left)

The Runs Panel is located on the left side of the debugger interface and provides comprehensive information about workflow executions. This panel is divided into two main tabs: Runs and API Logs.

* **Runs**: Displays all workflow executions initiated within the workspace. This includes executions triggered by users or systems, providing details like the workflow name, date, and time.
* **API Logs**: Shows detailed API interactions for each workflow run, offering an in-depth look into HTTP requests and responses for debugging purposes.

### **Run Logs View**

The Run Logs on the Runs screen provides a step-by-step breakdown of the execution of a workflow. It includes real-time tracking of variables, system messages, and output generation. Here's a detailed breakdown of the components:

#### **Action Start and Metadata**

* **Timestamp**: Indicates when the action started.
* **Run ID**: A unique identifier for the run, useful for tracking and debugging.
* **Workflow**: The name of the workflow being executed, clearly displayed for quick identification.
* **Duration**: Total time taken for the execution of this action, shown on the far right.

#### **Sequential Logs**

Each action or event in the workflow is logged in order of execution. Key types of logs include:

#### **Variable Setting**

Shows when variables are set or updated during the run.

* Example: `Setting {{currentDate}} to "Dec 8, 2024 7:29 PM"`.

#### **Global Variable Updates**

Indicates updates to globally scoped variables, such as user ID, thread ID, or API keys. As the workflow executes, runtime variables are updated and displayed in real time in the right-hand panel.

* Example: `Setting {{global.username}} to "Luis"`.

#### **Launch Variables**

Displays inputs provided during the execution, including prompts, parameters, or configuration values.

#### **Programmatic Messages**

Explains actions for each step in the workflow such as loading a model, resolving a variable, or querying an external API, as well as the output of that step.

* Example: `Sending message: "Generate a name, function name, and description for the following prompt..."`.

#### Function Calls

Logs the invocation of custom functions, including function name and input parameters and displays results returned by the function.

#### **Highlighting**

Key updates are color-coded for clarity:

* **Green**: Successful actions.
* **Red**: Errors or failures.

#### **Billing Insights**

Every action is broken down into **Billing Events**, including:

* Token usage details for inference prompts and responses.
* Costs associated with specific actions, including external services like image generation or language models.
* A total cost summary for the entire workflow execution.

#### **Runtime Variables Panel (Right)**

The **Runtime Variables** panel on the right-hand side shows. The current state of variables as the workflow progresses and how variables are updated at each step, offering transparency into how data flows through the workflow.

### **API Logs View**

<figure><img src="../.gitbook/assets/API LOGs 2.png" alt=""><figcaption></figcaption></figure>

The **API Logs** tab captures and displays all API interactions related to workflow executions. in addition to the Run Logs each API log also includes:

<figure><img src="../.gitbook/assets/API LOGs 3 (1).png" alt=""><figcaption></figcaption></figure>

#### **HTTP Method**

POST or GET for each API request.

#### **Source Information**

IP address, API Key, and User Agent used in the call.

#### **Status Codes**

Indicates success or failure of each API call (e.g., 200 for success).

#### **Run Logs Panel (Right)**

Displays a sequential breakdown of actions performed during the run, including variable settings, programmatic messages, and system interactions.

#### **Request Body**

Contains the raw payload sent during the API call, detailing the workflow ID and input variables used for the execution.

**Example:**

```json
{
workerId: "aaaaaaaa-b253-42b0-a8b6-bbbbbbbb"
variables: {
url: ""
metadata: ""
pageContent: ""
fullText: ""
userSelection: ""
rawHtml: ""
}
workflow: "Main.flow"
callbackUrl: ""
progressUrl: ""
includeBillingCost: false
version: "draft"
}
```

#### **Response Body**

Shows the output returned from the workflow, highlighting success status, results, and any errors.

**Example:**

```json
{
success: true
threadId: "aaaaaaaa111111222222233333333"
thread: {
id: "34234dksa-9g8g-2345-967b-b5hgfhd7df"
appId: "4747g737-b253-42b0-a8b6-5858ghf838"
organizationId: "57574hghd-c547-421e-8c6b-668ghjdj248j"
userId: "01314cd1-609b-497a-a2eb-1fff70b19a45"
entryWorkflowId: "pp00gh45-7233-471e-9719-00gg95fjdj"
sourceThreadId: null
source: "api"
parentThreadId: null
name: "Initialized with API variables"
variables: {}
currentContinuationAction: {}
isRunning: false
hasContent: true
isFinished: false
isUnread: true
notifyOnComplete: false
dateCreated: "2025-07-01T14:21:49.995Z"
dateLastMessage: "2025-07-01T14:22:11.902Z"
error: null
posts: []
assets: []
}
result: {
question: "Can you tell us a bit about what you were hoping to achieve or learn with your request?"
options: null
}
}
```

#### **NPM Snippet, Raw Fetch Code, and cURL:**

* **NPM Snippet**: Ready-to-use JavaScript code that initializes the MindStudio client, executes the workflow, and retrieves results.
  * **Example:**

```javascript
import { MindStudio } from 'mindstudio';

// Initialize the client
const client = new MindStudio('ske111122222eff2eeaaaaaaaaaaaaaaa8d672dbe9876543248d3c5051caaaaaaaaaaaaa');
await client.init();

// Execute the workflow
const { success, result } = await client.workers.untitledAgent_62b16c4e.main({
  "url": "",
  "metadata": "",
  "pageContent": "",
  "fullText": "",
  "userSelection": "",
  "rawHtml": ""
});

if (success) {
  console.log(result); // {"question":"Can you tell us a bit about what you ...
}
```

* **Raw Fetch Code**: Shows a plain JavaScript `fetch` example for invoking the API directly.
  * **Example:**

```javascript
const response = await fetch(
  'https://v1.mindstudio-api.com/developer/v2/agents/run',
  {
    method: 'POST',
    headers: {
      Authorization: 'Bearer ske111122222eff2eeaaaaaaaaaaaaaaa8d672dbe9876543248d3c5051caaaaaaaaaaaaa',
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      workerId: 'aaaaaaaa-aaaa-aaaaaaa-aaaa-aaaaaaa',
      variables: {
        url: '',
        metadata: '',
        pageContent: '',
        fullText: '',
        userSelection: '',
        rawHtml: '',
      },
      workflow: 'Main.flow',
      version: 'draft',
    }),
  },
);
const data = await response.json();
```

* **cURL Command**: A command-line example for making API calls with all necessary headers and body.
  * **Example:**

```javascript
curl 'https://v1.mindstudio-api.com/developer/v2/agents/run' \
  -H 'Authorization: Bearer ske111122222eff2eeaaaaaaaaaaaaaaa8d672dbe9876543248d3c5051caaaaaaaaaaaaa' \
  -H 'Content-Type: application/json' \
  --data-raw '{"workerId":"aaaaaaaa-aaaa-aaaaaaa-aaaa-aaaaaaa","variables":{"url":"","metadata":"","pageContent":"","fullText":"","userSelection":"","rawHtml":""},"workflow":"Main.flow","callbackUrl":"","progressUrl":"","includeBillingCost":false,"version":"draft"}}'
```

## **Exporting Logs**

You can export the debugging logs by clicking on the **Export** button at the bottom right of the Run Logs for further analysis or to share with your team.
