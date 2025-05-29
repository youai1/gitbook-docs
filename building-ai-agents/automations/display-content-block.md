---
description: Presents messages or outputs directly to users
---

# Display Content Block

The **Display Content Block** allows you to present messages or outputs directly to users in your workflows. It is used for delivering dynamic content with support for markdown formatting.

## **Configurations**

### **Message**

Define the message you want to display to the user. The **Display Content Block** supports markdown formatting, allowing you to structure text, add emphasis, or include links for a polished presentation. Use <mark style="color:red;">`{{variables}}`</mark> to make the message dynamic.

[Learn about variables →](../variables/)

[Learn more about Markdown formatting →](../writing-prompts/#using-markdown-to-write-prompts)

#### **Example Message**:

```markdown
## Welcome to our app!
Here are your **next steps:**
1. Complete your profile.
2. Explore the features of {{productName}}.
3. Contact us [here](<https://example.com/support>) for assistance.
```

Learn more about markdown → \[PAGE: Writing Prompts with Markdown].

### Display an Image

```markdown
![Alt Text]({{myImageVariable}})
```

### Display Audio Player

```markdown
<audio src="{{myAudioVariable}}" controls /></audio>
```

### Display Video Player

```markdown
<video src="{{myVideoVariable}}"></video>
```
