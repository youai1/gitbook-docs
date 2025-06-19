---
description: Trigger an n8n workflow from MindStudio
---

# Run Node

## Configuration&#x20;

### Webhook URL

Enter the webhook URL that will trigger the workflow. For information on creating webhooks with n8n [visit there documentation.](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.webhook/)

### Data

Add the data you want to send to n8n using **Key Value pairs**. This section can include variables.&#x20;

### Output Variable

Save the results of the request to a variable. Example: `n8n_request`

## Advanced Settings

### HTTP Method

Select the method you want to use in the request. Options include:

* **GET:** Retrieve data without modifying any underlying resources.
* **POST:** Create or update a resource.
* **PATCH:** Make partial updates to an existing resource.
* **PUT:** Update an entire resource.
* **DELETE:** Remove a specified resource.
* **HEAD:** Retrieve only the header information.

### Authentication

Select the authentication type. Options include:

* **None**&#x20;
* **Basic Auth**
  * This requires you to include a **username** and **password**.

