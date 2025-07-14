---
description: Retrieve Google News search results in a MindStudio workflow
---

# Search Google News

{% embed url="https://www.youtube.com/embed/UcpYnTeASRo" %}

## Configuration

### Text&#x20;

Define the search query that will be sent to Google News. The search query can include variables.

### Output Variable&#x20;

Specify the name of the output variable that will store the results. Example: `GoogleNews_result`

### Format

Select the format you want to save the returned result as:

* **Plain Text**
* **JSON**

## Sample Output - Plain Text

```json
Title: Over 50 Cats Rescued from Storage Unit
Date: 03/04/2025
Location: Bucks County, Pennsylvania
Key Details:
- 53 cats discovered in "filthy" public storage unit
- Some animals found in serious medical condition
- Local animal rescue team conducted comprehensive rescue operation
- Ongoing investigation into potential animal hoarding situation

Title: Free Microchipping Event for Cats and Dogs
Date: 03/06/2025
Location: Oxford
Key Details:
- Community event offering free pet microchipping
- Scheduled for March 15
- Aims to support responsible pet ownership
- Open to both cats and dogs
```

## Sample Output - JSON

```json
[
    {
        "position": 1,
        "title": "Herding cats: It's past time to include pets in disease surveillance",
        "source": {
            "name": "Example News Source",
            "icon": "https://example.com/icon.jpg",
            "authors": [
                "John Doe",
                "John Doe",
                "John Doe"
            ]
        },
        "link": "https://example.com/article",
        "thumbnail": "https://example.com/thumbnail.jpg",
        "thumbnail_small": "https://example.com/small-thumbnail.jpg",
        "date": "03/04/2025, 09:33 AM, +0000 UTC"
    }
]
```

***

## Search Operators Reference

Your search query can include Google Search Operators, like `site:bbc.co.uk`  to only return news results from the BBC, or `when:24h`  to only return news results from the past 24 hours. See the below table for the full list of supported search operators.

| Operator / Parameter         | Purpose                                        | Example                                                          |
| ---------------------------- | ---------------------------------------------- | ---------------------------------------------------------------- |
| `"exact phrase"`             | Search for an exact phrase                     | `"Apple Watch Series 10"`                                        |
| words (space-separated)      | Search for any of several keywords             | `Nikon mirrorless`                                               |
| `-word`                      | Exclude a keyword                              | `NBA Playoffs -Celtics`                                          |
| `site:domain`                | Limit to a specific website                    | `Apple site:techradar.com`                                       |
| `when:[timeframe]`           | Filter by publication time frame               | `when:1d` for past 24 hours (or `when:1h`, `when:1w`, `when:1y`) |
| Combinations                 | Mix/search restrictively                       | `Apple site:pcmag.com when:1d -Meta -Microsoft -Google`          |
| `topic_token`                | Filter by Google News topic                    | (token provided by API / UI; e.g. Technology)                    |
| `publication_token`          | Filter by publisher                            | (token representing PCMag, Forbes, etc.)                         |
| `section_token` (with above) | Filter by subsection within topic/publisher    | (e.g. Artificial intelligence under Technology)                  |
| `story_token`                | Filter by a specific news story                | (e.g. “Samsung Galaxy Unpacked event”)                           |
| `so`                         | Sort grouped story results (with story\_token) | `so` (sort by date descending)                                   |
