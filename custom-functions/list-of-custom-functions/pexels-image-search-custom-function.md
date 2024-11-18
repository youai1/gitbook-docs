---
description: Automate searching for free stock images on Pexels.
---

# Pexels Image Search: Custom Function

## What is Pexels?

[Pexels](https://www.pexels.com/) provides cloud-based search for high-quality, free stock images.

## What Can I Do With MindStudio and Pexels?

Build a MindStudio AI that asks the app user:

* for a term or phrase in which to search for images
* how many search results to display

Automate the search and show the app user the results.

## What is Required for This Custom Function?

* Pexels account.
* Pexels API Key. [Create one here](https://www.pexels.com/api/). Note this URL for the [**API Key** setting](pexels-image-search-custom-function.md#api-key) in MindStudio’s Pexels Image Search Custom Function.
* AI model for your MindStudio AI that can display images. Claude 3 Haiku is a great choice.
* **Image Search (Pexels)** Custom Function.

## Configuration

### API Key

Enter your Pexels API key.

### Search Query

Enter the search term or phrase in which to find images. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores that search term in a User Input provided by the user. **Example:** `{{Search}}`

### Image Count

Enter how many images to return in the image search. Optionally, reference a Variable that stores the number of images to return in that search. 1 is the default. **Example:**

```
{{ItemNumber}}
```

### Output Variable

Enter the Variable in which to store the returned Pexels image search. Note to not use double curly braces when entering the Variable name into the **Output Variable** setting. **Example:**

```
Images
```
