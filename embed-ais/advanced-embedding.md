---
description: >-
  Use advanced embedding to track each a unique user id and map an app session
  to each.
---

# Advanced Embedding

## Overview

With advanced embedding the host website is able to provide a unique user id and map an app session to it. This allows app users to:

* save their sessions when they return to the embedded app, even if they close their browser.
* change devices on the same hosting website.

Note that advanced embedding is only available if your MindStudio [Workspace](../workspaces/what-is-a-workspace.md) is on the Pro plan or higher. See MindStudio's [Pricing](https://youai.ai/pricing) page.

## Best Practice

[Name your MindStudio AI](../publishing/app-details.md) to indicate if it is using [simple embedding](embed-an-ai-app.md) or advanced embedding. This helps after you embed your AI into target websites which type of embedding it is using.

## Open Advanced Embedding&#x20;

1. [Enable embedding](embed-an-ai-app.md).
2. Select the **Show Advanced Configurations** link at the bottom of the page.

## Authorize Domains

1. Enter the domain name of the website to embed into the **Authorized Domains** setting.
2. Select the **Save** button.

To authorize more than one domain:

1. Select the **+** icon.
2. Enter another domain into the **Domain** setting.
3. Continue preceding steps for additional domains.
4. Select the **Save** button after you have added all domains.

### Embed the Code

After the domains have been authorized, copy the **Embed Code (Advanced)** and paste it into an embed block on your third party website builder. This process will differ depending on the website builder you use.

Note that the embedding experience WILL NOT work on Google Website builders.
