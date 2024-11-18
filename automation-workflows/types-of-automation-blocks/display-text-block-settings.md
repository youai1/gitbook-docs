---
description: Configure settings for the Display Text block.
---

# Display Text Block Settings

## Add Text&#x20;

In the message configuration, add the text that will displayed to the user. You can call variables in the text by added double curly braces around your variable name. `Example: {{text}}.`

Note that the text will display to the user exactly as it is written in the message field.&#x20;

<div data-full-width="true">

<figure><img src="../../.gitbook/assets/Display text.png" alt=""><figcaption></figcaption></figure>

</div>

## Display Block Syntax

Responses will be displayed to the user exactly as it is written. You may also call `{{variables}}` that you’d like to display to the user. Here are some syntax examples to display variables in different ways.

**Display an image:**

```markdown
![]({{myVariable}})
```

**Display the audio player:**

```markdown
<audio src="{{myAudioVariable}}" controls /></audio> 
```

**Conditional Formating:**

```markdown
{{#if myVariable}} 
So something with {{myVariable}}
{{else}}
Do something else
{{/if}}
```
