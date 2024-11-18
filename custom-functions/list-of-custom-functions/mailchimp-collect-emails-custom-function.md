---
description: >-
  Build a MindStudio AI that captures sales leads provided by the app user and
  automatically add them to your MailChimp mailing list.
---

# MailChimp - Collect Emails: Custom Function

## What is MailChimp?

[MailChimp](https://mailchimp.com/switch-to-mailchimp/) is a cloud-based email marketing platform to create, send, and track engaging email campaigns, automate emails, and manage mailing lists.

## What Can I Do With MindStudio and MailChimp?

Build a MindStudio AI that captures sales leads provided by the app user and automatically add them to your MailChimp mailing list.

## What is Required for this Custom Function?

* MailChimp account.
* MailChimp API Key. See [Get MailChimp API Key](mailchimp-collect-emails-custom-function.md#get-mailchimp-api-key).
* List ID for the mailing list to add sales leads. See [Get List ID](mailchimp-collect-emails-custom-function.md#get-list-id).
* Data center. See [Get Data Center](mailchimp-collect-emails-custom-function.md#get-data-center).
* **MailChimp - Collect Emails** Custom Function.

## Get MailChimp Settings for This Custom Function

### Get MailChimp API Key

1. Login to your Mailchimp account.
2. Navigate to your account settings.
3. Select the **Account & billing** option.
4. From the **Extras** menu, select the **API keys** option.
5. From the **Your API keys** section, select the **Create an API key** button.
6. In the **API Key Name** setting, enter a name for your API key.
7. Select the **Generate Key** button.
8. Select the **Copy to Clipboard** button to copy the new API key.
9. Store the API key for the [**API Key** setting](mailchimp-collect-emails-custom-function.md#api-key) in MindStudio’s MailChimp Collect Emails Custom Function.

### Get List ID

1. Navigate to the **All contacts** option in the left-side pane in MailChimp.
2. From the **Settings** menu, select the **Audience names and defaults** option.
3. Locate the **Audience ID** field.
4. Copy the value in the **Audience ID** field. Store the Audience ID value for the [**List ID** setting](mailchimp-collect-emails-custom-function.md#list-id) in MindStudio’s MailChimp Collect Emails Custom Function.

### Get Data Center

From your API key, note the characters after the hyphen (`-`). The data center code does not include the hyphen. **Example:**

```
us10
```

## Configuration

### API Key

Enter your MailChimp API key.

### List ID

Enter the list ID for the mailing list to add email addresses.

### Data Center

Enter the data center designation for your MailChimp account.

### Input

Enter the email address to add to the MailChimp mailing list. Optionally, reference a [Variable](../../user-inputs-and-variables/what-is-a-variable.md) that stores that email address that the app user enters into a User Input. **Example:**

```
{{email}}
```
