---
description: >-
  Run AI Agents directly inside your browser using the MindStudio Chrome
  Extension — perfect for real-time analysis, summarization, and more.
---

# AI Agents for Chrome Extension

{% embed url="https://youtu.be/JlDqei_-THY" %}

## Overview

The MindStudio Chrome Extension allows you to run AI Agents directly on web content while browsing. These Agents can analyze articles, extract key insights, summarize videos, or process PDFs — all without leaving the page.

#### Agents designed for the Chrome Extension are ideal for:

* **Content Summarization**: TL;DR summaries of articles, PDFs, or YouTube videos.
* **Conversation Analysis**: Evaluate X (Twitter) threads, Reddit posts, or comment sections.
* **PDF Review**: Summarize and extract insights from technical reports, legal filings, or financial documents.
* **Live Research**: Run product comparisons, SEO audits, or business lookups from within any site.
* **Study Aids**: Summarize lecture transcripts, educational videos, or online textbooks.
* **Custom Tools**: Create one-click utilities for internal documentation, competitor analysis, or code review.
* **Hundreds of other use cases!**

## How It Works

AI Agents configured for the Chrome Extension use the **Browser Extension** run mode.&#x20;

<figure><img src="../.gitbook/assets/Scheduled 1.png" alt=""><figcaption></figcaption></figure>

When you launch the Agent from your extension dock, it gains access to a set of launch variables pulled from the current page:

<figure><img src="../.gitbook/assets/Scheduled 2.png" alt=""><figcaption></figcaption></figure>

* `url` – The full URL of the current page
* `metadata` – Metadata from the page (e.g., title, description tags)
* `pageContent` – The main readable text content of the page (or transcript if YouTube)
* `fullText` – The entire body text (broader than `pageContent`)
* `userSelection` – Any text the user has highlighted
* `rawHtml` – The full HTML of the page

The Agent uses these values as context to power its workflow. The output is rendered directly inside the extension sidebar — giving you instant results without switching tabs or copying content.

## Key Features

* **Real-Time Page Processing**: Use AI to analyze or summarize the exact page you're on.
* **YouTube Support**: Automatically pulls and summarizes video transcripts.
* **PDF Compatibility**: Extracts and processes full text from in-browser PDFs.
* **Preconfigured Launch Variables**: No setup required — data is passed in automatically.
* **One-Click Launch**: Agents appear in your Chrome Extension dock for fast access.

## Setup Requirements

To configure an AI Agent for the Chrome Extension:

* Open the **Start Block** in your workflow.
* Set the **Run Mode** to `Browser Extension`.
* Use launch variables (like `{{page_content}}`) to bring in page data.
* Add logic blocks (e.g., Generate Text, Extract Entities) to process the content.
* Click **Publish** when ready.
* Open the **Published** tab → Click the three-dot menu → Select **Pin to Extension**.

Once published, your Agent will appear in your MindStudio Chrome Extension and can be run on any webpage in your browser.
