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
* **Event-Driven**: Based on external inputs like API requests.

### **Launch Variables**

Variables that are initialized at the start of the workflow and passed through the entire process. Launch variables can be referenced throughout the workflow using `{{variable_name}}`.

***

## Scheduling Workflow Runs

The **Scheduler** is a feature within the Start Block that allows you to set up automated, time-based triggers for your workflow. To enable the Scheduler, change the **Triggers > Run Mode** configuration from “On-Demand” to “Scheduled”. You may create multiple schedules for a workflow.

### Creating Schedules

1. **Define the Schedule** using natural language to describe how often and when the workflow should run.
   * Examples:
     * "Every day at 8:00 AM"
     * "Every Monday and Wednesday at 3:00 PM"
     * "First day of every month at 9:00 AM"
2. **Set the Time Zone** based the relative hours you’d like the workflow to run .
3. **(Optional) Add Launch Variable arguments** using `key:value` \*\*\*\*pairs.
4. Generate the Schedule by clicking on the **Generate Schedule Button**
5. **Save** the schedule.
