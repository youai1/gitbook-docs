---
description: Retrieve Google News search results in a MindStudio workflow
---

# Search Google News

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
