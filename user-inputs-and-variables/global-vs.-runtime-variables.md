---
description: Learn the difference between Global Variables versus Runtime Variables.
---

# Global vs. Runtime Variables

## Overview

A [Variable](what-is-a-variable.md) stores a value that represents data passed through the AI model. That data provides the context for the AI’s functionality and how it interacts with the user.&#x20;

## Global Variables

Global Variables store data that remains consistent and is built into the [Onboarding](../ai-app-settings/set-global-settings.md#onboarding) flow of your AI. Each user provides the data for Global Variables during first use of the app. Users are not prompted with Onboarding inputs with every new thread.&#x20;

**Examples of Global Data:** Company info, brand documents, training materials, and guides.

## Runtime Variables

Runtime Variables store data collected inside of the [Automation Workflow](../automation-workflows/what-is-an-automation-workflow.md). This data typically changes with every session and will be collected every time a new thread starts.&#x20;

**Examples of Runtime Data:** Customer info, Point of Contact info, and specific data queries.
