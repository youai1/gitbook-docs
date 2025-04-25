---
description: Fetch captions from a YouTube video in a MindStudio workflow
---

# Fetch YouTube Captions

{% embed url="https://www.youtube.com/embed/6z-L5tPndeQ?si=RuIBWnmz4-N-_5ef" %}

## Configuration&#x20;

### Video URL

Enter the URL for the Youtube video you want to fetch. This section can include variables.&#x20;

### Output Variable

Save the video captions to a variable. Example: `Youtube_Captions`

### Format

Select the format you want the captions to be exported as. The options include:

* **Plain Text**&#x20;
* **JSON**

### Language

Select the language you want to export the video captions as. English is selected by default.&#x20;

## Sample Output - Plain Text

```json
[00:05] Lorem ipsum dolor sit amet, consectetur adipiscing elit.

[00:07] Nullam vestibulum quam nec volutpat malesuada.

[00:09] Fusce tempor magna mi, non hendrerit lectus pulvinar vel.

[00:12] Sed euismod, velit vel bibendum bibendum,

[00:13] velit sapien bibendum massa,

[00:15] et aliquam nisl nunc vel massa.

...
```

## Sample Output - JSON

```json
[
    {
        "text": "Lorem ipsum dolor sit amet",
        "start": 5.779,
        "duration": 3.881
    },
    {
        "text": "consectetur adipiscing elit",
        "start": 7.98,
        "duration": 4.199
    },
    {
        "text": "sed do eiusmod tempor incididunt",
        "start": 9.66,
        "duration": 4.139
    }
]
```
