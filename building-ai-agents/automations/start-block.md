---
description: The first part of any workflow in MindStudio
---

# Start Block

The **Start Block** is the first part of any workflow in MindStudio. It initializes your AI Agent, defines how and when the workflow begins, and sets up key variables that are used throughout the workflow.

## Configurations

### **Triggers**

Define how the workflow is activated. Triggers can be configured to run:

* **On-Demand**: The default trigger. Requires manual execution.
* **Scheduled**: At specific times or intervals, such as daily at 8:00 AM.
* **Event-Driven**: Based on external inputs like API requests, webhooks, email.

### **Launch Variables**

Variables that are initialized at the start of the workflow and passed through the entire process. Launch variables can be referenced throughout the workflow using `{{variable_name}}`.

Launch variables can be defined in different ways, depending on the how the workflow is being started. They can be:

* Set in the body of an API request
* Defined in the settings of a [Run Workflow](run-workflow-block.md) block, if the workflow is being started by another workflow
* Defined in the schedule rules (see below) for scheduled runs
* Passed via query string parameters to the URL of the agent (e.g., `https://app.mindstudio.ai/agents/agent_id/run?variableName=variable_value&anotherVariable=different_value`). Note that this pattern also works for Signed URLs and Guest Access embeds.

***

## Run Modes

### On-Demand

The default mode for new Agents. These workflows only run when manually triggered by a user or system.

***

### Schedule

The **Scheduler** is a feature within the Start Block that allows you to set up automated, time-based triggers for your workflow. To enable the Scheduler, change the **Triggers > Run Mode** configuration from “On-Demand” to “Scheduled”. You may create multiple schedules for a workflow.

#### Creating Schedules

1. **Define the Schedule** using natural language to describe how often and when the workflow should run.
   * Examples:
     * "Every day at 8:00 AM"
     * "Every Monday and Wednesday at 3:00 PM"
     * "First day of every month at 9:00 AM"
2. **Set the Time Zone** based the relative hours you’d like the workflow to run .
3. **(Optional) Add Launch Variable arguments** using `key:value` \*\*\*\*pairs.
4. Generate the Schedule by clicking on the **Generate Schedule Button**
5. **Save** the schedule.

***

### Browser Extension

Triggered directly via [Chrome Extension](../../get-started/mindstudio-chrome-extension.md) while browsing the web. Enabling users to run Agents on the current page or selected content. Data from the page you are browsing are extracted as Launch Variables through the workflow.

**Launch Variables:**

* **`url`** - the URL of the page you are browsing
* **`metadata`** - A dictionary of metadata including page title, description, and other OpenGraph data when available.&#x20;
* **`pageContent`** - All main content extracted from the visible portion of the page. ON sites like youtube, pageContent is also used to extract the video transcript.
* **`fullText`** - A complete text dump of the page, including hidden and non-visible content.
* **`userSelection`** - The text manually highlighted by the user (if any) at the time the Agent is triggered.
* **`rawHtml`** - The full HTML source of the page

***

### Email Run

Triggered by sending an email to a unique, agent-specific email address. This mode is useful for processing inbound email data or automating responses. Content from the email are passed as Launch Variables through the workflow.

**Launch Variables:**

* **`from`** - the URL of the page you are browsing
* **`subject`** - A dictionary of metadata including page title, description, and other OpenGraph data when available.&#x20;
* **`message`** - All main content extracted from the visible portion of the page. ON sites like youtube, pageContent is also used to extract the video transcript.
* **`attachments`** - A complete&#x20;

***

### Webhook Run

Use this mode to start workflows automatically in response to external webhooks. The webhook endpoint is generated for each workflow and can be connected to other tools or services. Data sent in the webhook payload (e.g., JSON body) is mapped to Launch Variables, enabling full dynamic control over workflow behavior.&#x20;
