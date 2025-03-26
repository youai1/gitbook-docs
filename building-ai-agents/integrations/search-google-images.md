---
description: Retrieve Google Image search results in a MindStudio workflow
---

# Search Google Images

## Sample Output - Plain Text

```json
Title: Domestic Cat Sample
URL: https://example.com/sample-cat-image.jpg
Dimensions: 1920px x 1280px
Source: www.example.com

Title: Cat Sample Image
URL: https://example.com/another-cat-image.jpg
Dimensions: 1600px x 1024px
Source: www.sample-source.com

Title: Cat Breed Representation
URL: https://example.com/cat-breed-image.jpg
Dimensions: 1440px x 900px
Source: www.cat-example.org
```

## Sample Output - JSON

```json
[
  {
    "title": "Example Cat Image",
    "imageUrl": "https://example.com/placeholder-cat-image.jpg",
    "imageWidth": 1000,
    "imageHeight": 800,
    "thumbnailUrl": "https://example.com/placeholder-cat-thumbnail.jpg",
    "thumbnailWidth": 275,
    "thumbnailHeight": 183,
    "source": "Example Source",
    "domain": "example.com",
    "link": "https://example.com/cat-information",
    "googleUrl": "https://example.com/google-image-link",
    "position": 1
  }
]
```
