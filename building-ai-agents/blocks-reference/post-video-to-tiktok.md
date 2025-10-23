---
description: Post a TikTok Video
---

# Post Video to TikTok

The **Post Video to TikTok Block** allows you to post videos directly to your TikTok account. Control the level of privacy to your own account, your followers, or mutually following friends. This block is perfect for posting video content that you generate using MindStudio to TikTok.

## **Configurations**

### **Connection**

Create a new connection to your TikTok account. To do this requires a web application created on [TikTok for Developers](https://developers.tiktok.com/) with a Client ID and a Client Secret. This web app provides a Client ID and a Client Secret from which to connect to your TikTok account.

You can test posting TikTok videos to your account using a Sandbox environment, but only to yourself. To post to your followers or mutually following friends, you must submit your web app for approval to production.

1. From your consumer TikTok account, go to [**Settings**](https://www.tiktok.com/setting), then enable **Private account** from the **Privacy** settings.
2. Create a [TikTok for Developers](https://developers.tiktok.com/doc/add-a-sandbox/) account. This is separate from a consumer TikTok account.
3. Create a web app in a [Sandbox environment following these TikTok guidelines](https://developers.tiktok.com/doc/add-a-sandbox/). Ensure to do the following:
   1. Install the [Login Kit](https://developers.tiktok.com/doc/login-kit-overview?enter_method=left_navigation), which adds the "user.info.basic" scope to your web app.
   2. Install the [Content Posting API](https://developers.tiktok.com/doc/content-posting-api-get-started?enter_method=left_navigation), which adds the "video.publish" and "video.upload" scopes. Enable the **Direct Post** setting.
   3. Add your TikTok user name in the **Target Users**. This allows your TikTok account to connect to your web app and use the Sandbox environment.
4. Create the connection from the Post Video to TikTok Block or from the [**Integrations**](../../workspace-management/integrations.md) page on MindStudio. Do the following:
   1. Add the Client ID and Client Secret from your TikTok web app.
   2. Copy the **Redirect URL** from the Post Video to TikTok Block and paste it into **Redirect URL** in the Login Kit settings, then save the web app settings.
5. Connect to your TikTok account.

When successfully connected, your TikTok connection displays in [**Integrations**](../../workspace-management/integrations.md):

* **Active Connections:** Your TikTok account displays. From Access Control set who has access to your active connection:
  * Only Me
  * Anyone in this Workspace
* **Custom OAuth Provider Configurations:** The Client ID and Client Secret to your TikTok web app displays.

### **Video URL and Caption**

Choose the video by its URL and the video caption to post to TikTok.

* **Video URL**: Enter the URL for the video to post. You may include variables.
* **Caption**: Enter the caption for the video. You may include variables.

### **Advertising Disclosures**

Disclose whether your video is an advertisement.

* **Third-Party Brands:** Select if the video promotes any third-party businesses.
* **Your Own Brand:** Select if the video promotes your own business.

### **Post Settings**

Select post settings for the TikTok video.

* **Privacy Level:** Select who can view your TikTok video post. Use **SELF ONLY** when testing in a TikTok Developer Sandbox environment. Use other options only after TikTok approves your web app to production.
* **Comments:** Select whether others can comment on your video post.
* **Duets:** Select whether to allow Duets using your video post. **Allow Duets** is disabled if **Privacy Level** setting is set to **SELF ONLY**.
* **Stitches:** Select whether to allow Stitches using your video post. **Allow Stitches** is disabled if **Privacy Level** setting is set to **SELF ONLY**.

See [TikTok content sharing guidelines](https://developers.tiktok.com/doc/content-sharing-guidelines/) for more information.
