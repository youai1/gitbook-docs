---
description: Create a new Data Source to integrate custom data to your AI.
---

# Create A Data Source

## Overview

A [Data Source](what-is-a-data-source.md) allows the AI model to leverage additional information beyond its default training data. This provides a simple way to customize the AI's knowledge for your specific needs.

## Create A Data Source

1. Navigate to the **Data Source** folder in the **Explore** tab in the left-side panel.
2. Select the (**+**) icon.
3. Provide a name for the Data Source.
4. Optionally, provide a description for the Data Source.

Upload a single or multiple files. File types include:

* PDF (.pdf)
* CSV (.csv)
* Word Document (.docx)
* Excel Spreadsheet (.xlsx)
* Text File (.txt)
* HTML File (.html)

Note that uploading the file(s) DOES NOT mean the AI knows everything about your file(s). You must instruct the AI on how to query that file for the AI to use your Data Source properly. See [Query Data Source Block Settings](../automation-workflows/types-of-automation-blocks/query-data-block-settings.md).

Note that limits for uploading files are:

* 500 MB per file&#x20;
* 500k words per file
* 150 files maximum per Data Source
