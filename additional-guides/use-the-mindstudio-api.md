---
description: Learn how to activate API functionality for your app.
---

# Use the MindStudio API

## Overview

With the MindStudio API you can enable the programmatically invocation of workflows. It allows for the integration of AI workflows as a step in larger automation processes.

## Run an app

Executes a specified app with given variables and optional workflow.

### Endpoint

```bash
POST /developer/v2/apps/run
```

### Authentication

This endpoint requires Bearer token authentication.Request body

| Field       | Type   | Description                                   | Required |
| ----------- | ------ | --------------------------------------------- | -------- |
| workflow    | string | The workflow to run (without .flow extension) | No       |
| variables   | object | The variables to pass to the app              | No       |
| callbackUrl | string | The URL to receive the execution result       | No       |
| appId       | string | The ID of the app to run                      | Yes      |

### Response

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

### Example usage

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
    "callbackUrl": "https://your-callback-url.com/endpoint"
  })
});
const data = await response.json();
console.log(data);
```

Note: Replace <mark style="color:blue;">`YOUR_ACCESS_TOKEN`</mark> and <mark style="color:blue;">`YOUR_APP_ID`</mark> with your actual Bearer token and app ID, and adjust the request body according to your specific app requirements.

## Load an app

Loads an app by ID. If the app is not found, it returns a 404 error.

### Endpoint

```bash
GET /developer/v2/apps/load
```

### Authentication

This endpoint requires Bearer token authentication.

### Response

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

### Example usage

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

The syntax for calling a launch variable will be different than calling a variable on runtime. Rather than using <mark style="color:blue;">`{{VARIABLE_NAME}}`</mark> in your prompt, launch variables are called using <mark style="color:blue;">`{{$launchVariables->VARIABLE_NAME}}`</mark> syntax.

This must be utilized anytime a launch variable is called within a workflow. In the following example, we will look at the body of an API request that passes a launch variable, <mark style="color:blue;">`topic`</mark>, when running a MindStudio workflow.

### Example API request body

Within the body request, the launch variable <mark style="color:blue;">`topic`</mark> is assigned with the value “Dogs”.

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

Note: Replace <mark style="color:blue;">`YOUR_APP_ID`</mark> with your actual app ID.Example promptWithin a prompt area inside of Mindstudio, the <mark style="color:blue;">`topic`</mark> launch variable is called using the launch variable syntax.

{% code overflow="wrap" %}
```json
Assistant will write a blog post about the following topic:
{{$launchVariables->topic}}
```
{% endcode %}
