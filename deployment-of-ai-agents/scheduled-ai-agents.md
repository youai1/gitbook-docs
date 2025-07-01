---
description: >-
  Automate recurring tasks by running your AI Agent on a regular schedule — no
  manual triggering required.
---

# Scheduled AI Agents

{% embed url="https://youtu.be/pIIu2LuJR8g" %}

## Overview

Scheduled AI Agents are designed to run automatically at defined times — daily, weekly, monthly, or on any custom schedule you choose. These agents are ideal for automating repetitive tasks, monitoring changing content, or sending regular updates without requiring user input each time.

#### Common examples include:

* **Website Monitoring**: Detect changes to specific pages (e.g. pricing, press releases, documentation) and summarize them via email.
* **Daily Briefings**: Compile news or content from multiple sources and email a summary every morning.
* **Automated Reports**: Generate and send recurring business reports, sales insights, or analytics summaries.
* **Content Generation**: Create daily blog posts, product descriptions, or social content based on templates and external data.
* **Lead Follow-Up**: Process new entries in a lead database and send follow-up emails or update CRM fields automatically.
* **Task Cleanup**: Run daily database cleanups, data validations, or workflow triggers in integrated systems.
* **System Health Checks**: Monitor uptime, latency, or other metrics and notify stakeholders on a fixed schedule.
* **Internal Reminders**: Send team reminders for daily standups, sprint check-ins, or recurring to-dos.

## How It Works

A Scheduled Agent starts its workflow at the time(s) you configure. It uses the Start Block's **Run Mode** set to `Scheduled`, which allows you to define exactly when and how often the Agent should run.

During each run, the Agent performs its full workflow just like an on-demand Agent — pulling data, processing logic, generating output, and sending notifications.

## Key Features

* **Custom Schedules**: Use natural language to define when the Agent runs.
* **Timezone Support**: Run Agents in your local time or any global timezone.
* **Background Execution**: No user interaction required — Agents run silently.
* **Conditional Logic**: Combine with detection or alert logic for intelligent behavior.
* **Launch Variables**: Optional input variables allow for dynamic workflows at runtime.

## Setup Requirements

To configure an AI Agent to run on a schedule:

1. **Open the Start Block** in your workflow.
2. In the **Trigger** section, change the **Run Mode** from `On-Demand` to `Scheduled`.

<figure><img src="../.gitbook/assets/Schedule trigger mode.png" alt=""><figcaption></figcaption></figure>

1. Click **Add** to create a new schedule.
2. Use natural language (e.g., “every morning at 9 a.m.”) or select from preset options.

<figure><img src="../.gitbook/assets/Create schedule.png" alt=""><figcaption></figcaption></figure>

1. Choose the appropriate **time zone**.
2. (Optional) Configure **launch variables** if your Agent supports dynamic input.
3. Click **Generate Schedule**, then **Save**.

<figure><img src="../.gitbook/assets/Save schedule.png" alt=""><figcaption></figcaption></figure>

Once saved, your Agent will automatically run based on the schedule you’ve defined.

{% hint style="info" %}
**Pro Tip:** You may create as many schedules per agent as you'd like.
{% endhint %}
