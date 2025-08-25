---
description: Design interactive user input interfaces that fit your use case.
---

# Interface Designer

## Overview

The **Interface Designer** allows you to **vibe-code and customize** the way users interact with your AI agents. Instead of relying only on default input forms, you can define branded, multi-step, or interactive interfaces that better fit your use case.

Examples include: onboarding flows, feedback forms, quiz-style apps, or creative tools like interactive drawing-to-AI experiences.

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 1.26.04 PM.png" alt=""><figcaption></figcaption></figure>

## How It Works

When adding a **User Input block** in a workflow, you can switch the **Interface** option from the default to **Custom (Beta)**.&#x20;

From here, the **Configure Interface** button opens the Interface Designer, where you can:

* Use conversational "vibe coding" to describe the interface you want.
* See a live preview of the generated UI.
* Access the generated code and edit it directly if needed.
* Compile and publish the interface for use in your agent.

## Setup Requirements

1. Add a **User Input** block to your workflow.
2. In **Optional Settings**, switch **Interface** to **Custom (Beta)**.
3. Click **Configure Interface** to launch the Interface Designer.
4. Describe your UI or edit the generated code directly.
5. Use **Preview Window** to view changes in real time.
6. Click **Compile** to build and attach the interface to your agent.

## Key Controls

### **Chat Tab**

The **vibe-coding interface**. Use the Chat tab to describe what you’d like your interface to look like, and the AI will generate it for you. You can refine designs by giving iterative instructions such as adjusting layout, styling, or flow.

{% hint style="info" %}
**Pro Tip:** Start with simple instructions (e.g., “Create a form with name and email fields”) and iteratively refine using vibe coding for faster results.
{% endhint %}

### **Code Tab**

The **Code tab** provides a complete, production-grade coding environment for your custom interface. Beyond simply viewing the AI-generated React code, you can fully edit and extend it as if you were working in a professional IDE.

#### **Key capabilities:**

* **Full React environment**: Write and edit JSX, manage components, and structure your UI as you would in any React app.
* **Package management**: Install additional npm packages directly within the environment to extend functionality.
* **Hot reloading**: See your changes instantly reflected in the **Live Preview** without restarting the session.
* **Advanced customization**: Add API integrations, validation logic, dynamic data loading, or embed third-party libraries.
* **Production readiness**: Once compiled, the code is packaged and deployed as part of your agent, ensuring it runs reliably in real use cases.

### **Logs Tab**

A real-time activity feed that shows what’s happening behind the scenes. Use Logs to debug issues, track package installs, or understand how the interface is running.

### **Live Preview**

An interactive preview window where changes are rendered instantly. Use it to test behavior, styling, and flow before compiling your interface.

### **Model Selector**

Located in the bottom-right of the Interface Designer.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 1.05.12 PM.png" alt="" width="375"><figcaption></figcaption></figure>

Defines which model powers the interface generation process. This follows your **workspace model settings** by default, but can be adjusted to use different models depending on your project’s needs.

### Dev Environment Controls

Located at the bottom left of the Interface Designer, these controls let you manage the development lifecycle of your custom UI.

<figure><img src="../.gitbook/assets/Screenshot 2025-08-25 at 2.05.30 PM.png" alt=""><figcaption></figcaption></figure>

#### Start

Begins a live preview session of your interface. This spins up the development environment and renders changes in real time as you edit or vibe code.

#### Stop

Ends the current preview session. This is useful for freeing up resources when you’re not actively working on the interface.

#### Compile

Builds and deploys your custom interface into your agent. After compiling, the UI is packaged, uploaded, and made available in production. This ensures that when your agent runs, it uses the finalized version of your interface.

