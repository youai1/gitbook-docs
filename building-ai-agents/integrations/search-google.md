---
description: Retrieve Google search results in a MindStudio workflow
---

# Search Google

## Configuration

### Search Query&#x20;

Type in the text query that will be sent to Google. The search query can include variables.&#x20;

### Output Variable&#x20;

Specify the name of the output variable that will store the results. Example: `googleSearch_results`

### Format

Select the format you want to save the returned result as:

* **Plain Text**
* **JSON**

## Sample Output - Plain text

```json
Title: [Topic] - Wikipedia
Description: [Brief overview of topic with generic information]
URL: https://en.wikipedia.org/wiki/[Topic]

Title: [Topic] Explained - Expert Guide
Description: Comprehensive breakdown of key concepts, history, and current trends in [topic area]
URL: https://www.example-expert-site.com/guide/[topic]

Title: Top [Number] [Topic] Insights
Description: In-depth analysis of [topic] including recent developments and important considerations
URL: https://www.research-platform.com/insights/[topic]

Title: Understanding [Topic]: A Complete Resource
Description: Detailed exploration of [topic], covering essential aspects and practical applications
URL: https://www.learning-center.org/[topic]-guide
```

## Sample Output - JSON

```json
[
    {
        "title": "Example Website",
        "description": "Placeholder website description",
        "url": "https://example.com/"
    },
    {
        "title": "Another Website",
        "description": "Generic website description",
        "url": "https://example-b.org"
    }
]
```
