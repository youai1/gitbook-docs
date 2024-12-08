---
description: Integrate MindStudio AI Workers with Make.com
---

# Make.com + MindStudio

This guide provides step-by-step instructions on integrating Make.com with MindStudio AI Workers. With this integration, you can trigger workflows directly from Make.com using your MindStudio app and easily pass variables to your flows.

{% @supademo/embed demoId="cm2adbsqz08x34irjspr7813i" url="https://app.supademo.com/demo/cm2adbsqz08x34irjspr7813i" %}

***

## Steps to Set Up the [Make.com](http://make.com) Integration

### 1. Adding the MindStudio App

1. Begin by adding a new app connection to the Make canvas. Search for **MindStudio** in the app directory.
2. Select the desired action. Commonly, you'll choose **Run an App**, but you can also list all available apps or start an HTTP call.
3. Click on **Create a Connection**.

***

### 2. Connecting Your Workspace

1. Insert your workspace's API key. This API key connects Make to the MindStudio workspace where your app is hosted.
2. To retrieve the API key, click on the gear icon next to your workspace name in MindStudio.
3. In the sidebar menu, select **API** and navigate to **API Keys**.
4. Generate a new key by clicking **Create Key**, or copy an existing one.
5. Name the API key for internal use and click **Create** to finalize.
6. Copy the API key using the copy icon.

***

### 3. Configuring the Make Connection

1. Return to [Make.com](http://make.com) and paste the API key into the connection setup.
2. Save the connection.

***

### 4. Running a MindStudio App

1. Once connected, you can run any app in your workspace using its corresponding **App ID**.
2. To find an App ID, click on the app name in MindStudio (top left corner) to reveal and copy the ID.
3. Alternatively, navigate to the app list in MindStudio. Click the three dots next to the app name and select **Copy App ID**.

***

### 5. Setting Up Workflows and Variables

1. After entering the App ID, you can specify which workflow to run. If it's different from the default main workflow, enter the workflow name (excluding `.flow`).
2. To pass variables to the workflow, click on **Add Item** under the Variables section in Make.
3. Enter a **Variable Name** and assign a corresponding **Value**. The value can come from the output of a previous module or be formatted with Make's special syntax and operators.

***

### 6. Verifying the Integration

1. Click **OK** to complete the setup.
2. Test the module by right-clicking on it and selecting **Run this module only**.
3. Verify that the workflow executes successfully. Note: In this example, no variables were initialized, so ensure you pass variables to the flow if required for execution.

***

### Final Result

Congratulations! You've successfully integrated [Make.com](http://make.com) with MindStudio. With this setup, you can easily trigger and interact with MindStudio workflows directly from your Make modules.

This workflow was created with Supademo.
