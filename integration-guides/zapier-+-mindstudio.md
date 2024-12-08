---
description: Integrate MindStudio AI Workers with Zapier
---

# Zapier + MindStudio

This guide walks you through the steps to integrate MindStudio AI Workers with Zapier, allowing you to trigger workflows and seamlessly connect them to other apps like Slack. By following this tutorial, you can create a Zap that triggers when a Slack channel receives a new message and responds with the output from your MindStudio workflow.

{% @supademo/embed demoId="cm2wamwyo02i8krgpgl4574gl" url="https://app.supademo.com/demo/cm2wamwyo02i8krgpgl4574gl" %}

***

### Steps to Set Up the Zapier Integration

### 1. Setting Up the Trigger

1. Trigger the Zap with your chosen app. For this guide, we'll trigger it when a new message is received in a Slack channel.
2. Select **Slack** as the app.
3. Choose a trigger event, such as **New Channel Message**.
4. Select the trigger event from the list.
5. Choose an existing Slack connection or set up a new one.
6. Select the connection and click **Continue**.
7. Choose the Slack channel you want to monitor. In this example, we'll use a channel named `new-zapier-integration`.
8. Click **Continue**.
9. Test the trigger by selecting a sample message. For this guide, we'll use a message that says "hello".
10. Click **Continue with selected record**.

***

### 2. Adding MindStudio to the Workflow

1. Add a new step to the Zap and select **MindStudio** as the integration.
2. Click **Choose an Event** and select **Run Workflow**.
3. Connect your MindStudio workspace. You can use an existing connection or create a new one by generating an API key.
4. To connect a new account, click **Connect a new account**.
5. Retrieve your API key from MindStudio:
   * Click on your workspace name in the top-right corner.
   * Navigate to **Settings** > **API Keys**.
   * Copy an existing key or create a new one, name it for internal use, and click **Create**.
6. Paste the API key into the Zapier connection popup and click **Yes, Continue to MindStudio**.
7. Once connected, all your MindStudio apps will appear under the **App ID** dropdown. You can search by App ID or app name.
8. Select the appropriate app from the dropdown.

***

### 3. Configuring Workflow Variables

1. Pass variables to the workflow:
   * For our example, pass the Slack message content to the `message` variable in MindStudio.
   * Use the `/` symbol or the **+** icon in Zapier to select properties from the Slack trigger.
2. Choose the flow to run in MindStudio. Avoid using `.flow` unless it's the default.
3. Click **Continue** and test the step.

***

### 4. Adding the Slack Response Step

1. Add another step to send a response back to Slack.
2. Select Slack as the app and choose an action event.
3. Pick the same channel (`new-zapier-integration`) where the original message was received.
4. For the message text, select the **result** of the MindStudio workflow from the previous step.
5. If you want the response as a reply in the same thread, add the **ts** (timestamp) value from the trigger step:
   * Select **Custom Value** from the three-dot menu.
   * Choose **Ts** from the list.

***

### 5. Finalizing and Publishing

1. Click **Continue** and skip the test. Note that MindStudio workflows won’t execute during Zapier's test phase due to limitations, but the results can still be used.
2. Publish the Zap.

***

### Final Result

Now, whenever you send a message in the selected Slack channel, the MindStudio workflow will process the message and respond instantly in the same channel or thread.
