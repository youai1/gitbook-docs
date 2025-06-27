---
description: Learn about every block in MindStudio
---

# Blocks Reference

To effectively build and customize your workflows, there are hundreds of blocks available, each serving a specific function to streamline your processes and enhance integration capabilities.

## Workflow Blocks Reference

<table><thead><tr><th width="266">Block Name</th><th>Purspose</th></tr></thead><tbody><tr><td><a href="start-block.md">Start Block</a></td><td>Initializes the Workflow. Every Workflow includes a Start Block that cannot be deleted.</td></tr><tr><td><a href="generate-text-block.md">Generate Text Block</a></td><td>Uses AI to generate text based on a prompt. Responses can be displayed to human or assigned to a variable.</td></tr><tr><td><a href="generate-image-block.md">Generate Image Block</a></td><td>Uses AI to generate an image based on a text prompt. Image URL is assigned to a variable.</td></tr><tr><td><a href="generate-chart-block.md">Generate Chart Block</a></td><td>Generates a chart based on JSON Schema.</td></tr><tr><td><a href="display-content-block.md">Display Content Block</a></td><td>Displays content to the user exactly as it is written. Can call variables.</td></tr><tr><td><a href="text-to-speech-block.md">Text to Speech Block</a></td><td>Uses AI to generates a voice-over audio file that matches the provided text. Audio URL is assigned to a variable.</td></tr><tr><td><a href="user-input-block.md">User Input Block</a></td><td>Displays user inputs in a single-page form to gather context for the AI. Values from human inputs are assigned to variables.</td></tr><tr><td><a href="query-data-block.md">Query Data Block</a></td><td>Queries a Data Source and returns relevant chunks of text. Returned text is assigned to a variable.</td></tr><tr><td><a href="run-function-block.md">Run Function Block</a></td><td>Executes JavaScript code. Configurations and outputs will vary.</td></tr><tr><td><a href="analyze-image-block.md">Analyze Image Block</a></td><td>Uses AI to analyze the content of a provided image URL. Responses can be displayed to human or assigned to a variable.</td></tr><tr><td><a href="scrape-url-block.md">Scrape URL Block</a></td><td>Uses a web scraper to gather text from a URL. Returned text is assigned to a variable.</td></tr><tr><td><a href="extract-text-from-file-block.md">Extract Text from File Block</a></td><td>Extracts text from PDF, CSV, HTML, and TXT files</td></tr><tr><td><a href="post-to-slack-block.md">Post to Slack Block</a></td><td>Sends a message to a Slack channel</td></tr><tr><td><a href="menu-block.md">Menu Block</a></td><td>Creates branching paths in a workflow. Routes the workflow based on human selection.</td></tr><tr><td><a href="logic-block.md">Logic Block</a></td><td>Creates branching paths in a workflow. Routes the workflow based on AI selection.</td></tr><tr><td><a href="jump-block.md">Jump Block</a></td><td>Routes the workflow directly into another discrete workflow. Variables cannot be passed into the new workflow.</td></tr><tr><td><a href="run-workflow-block.md">Run Workflow Block</a></td><td>Runs a sub-workflow. Variables can be passed through the workflow as Launch Variables. Returns the output of the workflow.</td></tr><tr><td><a href="./#terminator-blocks">Terminator Block</a></td><td>Ends the workflow. Can be configured with different end behaviors such as a front-end chat interface, email notification, and more.</td></tr></tbody></table>

{% embed url="https://youtu.be/KNtIG6NdPMw" %}

Integrations in MindStudio connect various apps and services to your workflows. You can find all kinds of integrations by adding new blocks in the [automations](./) tab.

## Integration Blocks Reference

### Social Media Blocks

| Block Name                                                    | Purpose                                  |
| ------------------------------------------------------------- | ---------------------------------------- |
| [Search Bluesky Posts](search-bluesky-posts.md)               | Search for posts on Bluesky              |
| [Scrape Facebook Page](scrape-facebook-page.md)               | Get general details of a Facebook page   |
| [Scrape Meta Threads Profile](scrape-meta-threads-profile.md) | Get data from a Meta Threads profile     |
| [Scrape Instagram Comments](scrape-instagram-comments.md)     | Get Comments data from an Instagram post |
| [Scrape Instagram Mentions](scrape-instagram-mentions.md)     | Get data from mentions on Instagram      |
| [Scrape Instagram Posts](scrape-instagram-posts.md)           | Get posts from an Instagram profile      |
| [Scrape Instagram Profile](scrape-instagram-profile.md)       | Get data from an Instagram profile       |
| [Scrape Instagram Reels](scrape-instagram-reels.md)           | Get reels from an Instagram profile      |
| [Create LinkedIn Post](create-linkedin-post.md)               | Make a new post on LinkedIn              |
| [Create X Post](create-x-post.md)                             | Make a new post on X                     |
| [Search X Posts](search-x-posts.md)                           | Search for posts on X by keyword         |

### Google Blocks

| Block Name                                      | Purpose                                   |
| ----------------------------------------------- | ----------------------------------------- |
| [Search Google](search-google.md)               | Retrieve Google search results            |
| [Search Google Images](search-google-images.md) | Retrieve Google Image search results      |
| [Search Google Trends](search-google-trends.md) | Retrieve Google Trends keyword results    |
| [Search Google News](search-google-news.md)     | Retrieve Google News search results       |
| [Create Google Doc](create-google-doc.md)       | Create a new Google Doc document          |
| [Fetch Google Doc](fetch-google-doc.md)         | Retrieve content from a Google Doc        |
| [Update Google Doc](update-google-doc.md)       | Update values of an existing Google Doc   |
| [Create Google Sheet](create-google-sheet.md)   | Create a new Google Sheet document        |
| [Fetch Google Sheet](fetch-google-sheet.md)     | Retrieve content from a Google Sheet      |
| [Update Google Sheet](update-google-sheet.md)   | Update values of an existing Google Sheet |

### Hunter.io Blocks

| Block Name                                                | Purpose                            |
| --------------------------------------------------------- | ---------------------------------- |
| [Enrich Company via Domain](enrich-company-via-domain.md) | Enrich company data using a domain |
| [Find Contact Email for Website](find-email.md)           | Find emails for a given website    |
| [Find Email](find-email.md)                               | Find a person's email for a domain |
| [Verify Email](verify-email.md)                           | Verify a person's email address    |
| [Enrich Person via Email](enrich-person-via-email.md)     | Enrich person's data via email     |

### YouTube Blocks

| Block Name                                          | Purpose                                   |
| --------------------------------------------------- | ----------------------------------------- |
| [Fetch YouTube Captions](fetch-youtube-captions.md) | Fetch captions from a YouTube video       |
| [Fetch YouTube Channel](fetch-youtube-channel.md)   | Fetch details from a YouTube channel      |
| [Fetch YouTube Comments](fetch-youtube-comments.md) | Fetch all comments from a YouTube video   |
| [Fetch YouTube Video](fetch-youtube-video.md)       | Fetch details from a YouTube video        |
| [Search YouTube](search-youtube.md)                 | Retrieve YouTube search results           |
| [Search YouTube Trends](search-youtube-trends.md)   | Search for trends by a specified category |

### Notion Blocks

| Block Name                                                                                   | Purpose                 |
| -------------------------------------------------------------------------------------------- | ----------------------- |
| [Create Page](https://help.mindstudio.ai/building-ai-agents/integrations/create-notion-page) | Create a page in Notion |
| [Update Page](update-notion-page.md)                                                         | Update a page in Notion |

### Other Automations

| Block Name                                         | Purpose                                     |
| -------------------------------------------------- | ------------------------------------------- |
| [Apify](apify-block.md)                            | Run an Apify actor                          |
| [Run Scenario](run-scenario-make.md)               | Run a specified scenario on Make.com        |
| [Post to Slack](post-to-slack.md)                  | Send a message to a specified Slack channel |
| [HTTP Request](http-request.md)                    | Send an HTTP request                        |
| [Run Node](run-node-n8n.md)                        | Trigger an n8n workflow                     |
| [Create Contact](create-contact-activecampaign.md) | Create a contact in ActiveCampaign          |
| [Add Note](add-note-activecampaign.md)             | Add a note to a contact in ActiveCampaign   |
| [Send Email](send-email.md)                        | Send an email to a registered email address |
| [Send SMS](send-sms.md)                            | Send an SMS to a valid phone number         |
