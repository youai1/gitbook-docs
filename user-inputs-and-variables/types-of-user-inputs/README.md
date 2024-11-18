---
description: Learn the different ways to collect data from the app user.
---

# Types of User Inputs

## Overview

Depending on the type of data you plan on collecting from app users, there are different User Input types you can use. See [Create a User Input](../create-a-user-input.md) for more information on creating any of the following input types.

## Types of Inputs

### Long Text&#x20;

The Long Text input collects a large amount of plain text that can be typed or pasted in. This input type is best suited for collecting long form answers to questions or pasted in text from large files.

See [Long Text User Input Settings](long-text-user-input-settings.md).

### Short Text&#x20;

The Short Text input collects small amounts of plain text that can be typed or pasted in. This input type is best suited for collecting names, URLs, and geographical locations.

See [Short Text User Input Settings](short-text-user-input-settings.md).

### Text Choice

The Text Choice input allows selection of one or multiple text choices. By default, the text choice input displays two choices (Yes and No). This input type is best suited for Yes or No questions, multiple choice questions, and “Select all that apply” style questions.

See [Text Choice User Input Settings](text-choice-user-input-settings.md).

### Image Choice

The Image Choice input allows selection of one or multiple image choices instead of text. A text label attaches to each image that is stored when a user makes a selection.

See [Image Choice User Input Settings](image-choice-user-input-settings.md).

### Rating

The Rating input is a 1-5 selection input. Customize the left and right labels to identify the ratings scale.

See [Rating User Input Settings](rating-user-input-settings.md).

### Date&#x20;

The Date input is a date picker that expands a calendar to select a specific date.

See [Date User Input Settings](date-user-input-settings.md).

### Display

The Display input is a text and image display that does not require the user to input any information. The Display is best suited for instructions and guiding users through a Workflow.&#x20;

See [Display User Input Settings](display-user-input-settings.md).

### Scrape URL

The Scrape URL input collects a URL from the user and scrapes the text from the front page of that URL. Note that the Scrape URL cannot scrape images or additional pages inside of the URL provided.

See [Scrape URL User Input Settings](scrape-url-user-input-settings.md).

### Upload File

The Upload File input presents users with a media upload to collect data from text-based documents. The Upload File input accepts the following file types:

* Excel Spreadsheet (.xlsx)
* CSV File (.csv)
* Word Document (.docx)
* Text File (.txt)
* PDF (.pdf)
* HTML Document (.html)

Note that when a user uploads a file to an AI, the AI model processes the entire file. This may increase the number of tokens the AI model uses, and therefore the number of [billing credits](../../workspaces/manage-workspace-usage/#ai-inference) to run that AI.

See [Upload File User Input Settings](upload-file-user-input-settings.md).
