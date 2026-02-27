---
description: >-
  Use AI to generate lip-synced and/or translated video in your AI agents.
  Sources may include image, audio, and/or video.
---

# Lip Sync Video Block

This block generates a video that lip syncs or translates from source asset(s). Sources may include the following:

* audio+video
* image+audio
* video

## Configuration

### Output

#### Output Variable

Save the generated video URL to a variable that can be used in other parts of your workflow.

#### History Access

Include the output variable in the workflow's history or hide it. Set to **Include** by default.

#### Branding

Include a small MindStudio watermark on the video. **None** by default.

### Model Settings&#x20;

#### Select Model

* ByteDance LatentSync (audio+video)
* ByteDance Omni Human 1.5 (image+audio)
* HeyGen Video Translate (video)
* Kling AI Avatar Standard (image+video)
* MeiGen Infinitetalk (image+audio)

{% hint style="info" %}
Please note that different models will have different configuration settings.
{% endhint %}
