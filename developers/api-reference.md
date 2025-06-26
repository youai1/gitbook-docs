---
description: Run AI Agents via API request.
---

# API Reference

## Overview

With the MindStudio API you can enable the programmatically invocation of workflows. It allows for the integration of AI workflows as a step in larger automation processes.

## Run an app

Executes a specified app with given variables and optional workflow.

#### Endpoint

```bash
POST /developer/v2/apps/run
```

#### Authentication

This endpoint requires Bearer token authentication.Request body.

#### Parameters

<table><thead><tr><th width="199.1727294921875">Field</th><th width="91.40966796875">Type</th><th width="243.3472900390625">Description</th><th>Example</th></tr></thead><tbody><tr><td><code>workflow</code></td><td>string</td><td>The workflow to run (without .flow extension)</td><td><code>myWorkflowName</code></td></tr><tr><td><code>variables</code></td><td>object</td><td>The variables to pass to the app</td><td><p><code>{</code></p><p>  <code>"firstName":"John",</code></p><p>  <code>"lastName":"Smith"</code></p><p><code>}</code></p></td></tr><tr><td><code>callbackUrl</code></td><td>string</td><td>The URL to receive the execution result</td><td><code>https://myUrl.com/</code></td></tr><tr><td><kbd><code>appId</code></kbd></td><td>string</td><td>The ID of the app to run</td><td><code>46f2e54b-f2fv-4055-bbf4-h55555a7c3b6</code></td></tr><tr><td><code>includeBillingCost</code></td><td>boolean</td><td>Indicates whether or not you'd like the final cost returned in the response body.</td><td><code>true</code></td></tr></tbody></table>

#### Response

#### Success response (200 OK)

The response will be one of two possible formats:

1 - For asynchronous execution (when `callbackUrl` is provided):

```json
{
  "success": true,
  "callbackInProgress": true
}
```

2 - For synchronous execution:

```json
{
  "success": true,
  "threadId": "string",
  "thread": {
    // Full thread object
  },
  "result": "string" // Content of the last system message
}
```

#### Error responses

<mark style="color:red;">`400 Bad Request`</mark>: The request was invalid or cannot be served.

<mark style="color:red;">`500 Internal Server Error`</mark>: The server encountered an unexpected condition that prevented it from fulfilling the request.

#### Example usage

```javascript
const response = await fetch("https://api.mindstudio.ai/developer/v2/apps/run", {
  method: "POST",
  headers: {
    "Authorization": "Bearer {{YOUR_ACCESS_TOKEN}}",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    "appId": "{{YOUR_APP_ID}}",
    "variables": {
      "key1": "value1",
      "key2": "value2"
    },
    "workflow": "optional-workflow-name",
    "callbackUrl": "https://your-callback-url.com/endpoint",
    "includeBillingCost": true
  })
});
const data = await response.json();
console.log(data);
```

Note: Replace <mark style="color:blue;">`YOUR_ACCESS_TOKEN`</mark> and <mark style="color:blue;">`YOUR_APP_ID`</mark> with your actual Bearer token and Agent ID, and adjust the request body according to your specific app requirements.

#### Example Output

<pre class="language-javascript" data-overflow="wrap"><code class="lang-javascript">{
    success: true
    threadId: "9ca06a28-871b-407e-8f5d-f6d7b0b2e389"
    thread: {
        id: "00530fa6-33ef-4284-a4c4-41302d5fe379"
        appId: "46f2e54b-f2fv-4055-bbf4-h55555a7c3b6"
        organizationId: "79249296-1f88-47c5-9737-ab3679b9f872"
        userId: "83abb8d1-bd26-4148-ab41-759916dc7188"
        entryWorkflowId: "46bf354d-c2ab-4e5c-8230-504b0f58683b"
        sourceThreadId: null
        source: "api"
        parentThreadId: null
        name: "Title of the run"
        variables: {
            "key1":"value1",
            "key2":"value2"
        }
        currentContinuationAction: {...}
        isRunning: false
        hasContent: true
        isFinished: true
        isUnread: true
        notifyOnComplete: false
        dateCreated: "2025-06-25T23:54:19.287Z"
        dateLastMessage: "2025-06-25T23:54:36.398Z"
        error: null
        posts: [...]
        assets: [...]
    }
    result: {
<strong>        "myOutputVar1":"This is the final result of the run."
</strong>    }
    billingCost: "$0.011255850000000001"
}
</code></pre>

***

## Load an app

Loads an app by ID. If the app is not found, it returns a 404 error.

#### Endpoint

```bash
GET /developer/v2/apps/load
```

#### Authentication

This endpoint requires Bearer token authentication.

#### Response

#### Success response (200 OK)

The response will be a JSON object containing the organization information.

```json
{
  "orgId": "string",
  "orgName": "string"
}
```

#### Error response (404 Not Found)

The organization for the specified token was not found.

#### Example usage

```javascript
const response = await fetch("https://api.mindstudio.ai/developer/v2/apps/load", {
  method: "GET",
  headers: {
    "Authorization": "Bearer {{YOUR_ACCESS_TOKEN}}"
  }
});
const data = await response.json();
console.log(data);
```

Note: Replace <mark style="color:blue;">`YOUR_ACCESS_TOKEN`</mark> with your actual Bearer token.

## How to pass launch variables from an API request to a workflow

The syntax for calling a launch variable will be different than calling a variable on runtime. Rather than using <mark style="color:red;">`{{VARIABLE_NAME}}`</mark> in your prompt, launch variables are called using <mark style="color:red;">`{{$launchVariables->VARIABLE_NAME}}`</mark> syntax.

This must be utilized anytime a launch variable is called within a workflow. In the following example, we will look at the body of an API request that passes a launch variable, <mark style="color:red;">`topic`</mark>, when running a MindStudio workflow.

### Example API request body

Within the body request, the launch variable <mark style="color:red;">`topic`</mark> is assigned with the value “Dogs”.

```json
{
  "appId": "{{YOUR_APP_ID}}",
  "variables": {
    "topic": "Dogs"
  },
  "workflow": "workflow-name",
  "callbackUrl": "https://your-callback-url.com/endpoint"
}
```

Note: Replace <mark style="color:red;">`YOUR_APP_ID`</mark> with your actual app ID.Example promptWithin a prompt area inside of Mindstudio, the <mark style="color:red;">`topic`</mark> launch variable is called using the launch variable syntax.

{% code overflow="wrap" %}
```json
Assistant will write a blog post about the following topic:
{{$launchVariables->topic}}
```
{% endcode %}
