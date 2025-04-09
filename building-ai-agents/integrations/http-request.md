---
description: Request information from a web server to be used in your MindStudio workflows
---

# HTTP Request

## Configuration&#x20;

### URL

Enter a valid URL to send the request to. This section can include variables.&#x20;

### Method

Select the method you want to use from the dropdown menu. Options include:

* **GET:** Retrieve data without modifying any underlying resources.
* **POST:** Create or update a resource.
* **PATCH:** Make partial updates to an existing resource.
* **PUT:** Update an entire resource.
* **DELETE:** Remove a specified resource.
* **HEAD:** Retrieve only the header information.
* **OPTIONS:** Discover the communication options available for a specific resource.

### Headers

Use **Key Value pairs** to include HTTP headers in the request. This section can include variables.

### Parameters

Use **Key Value pairs** to add query parameters to further specify or filter the data requested. This section can include variables.

### Content Type

Select the content type for the request body. Options include:

* **text/plain**
* **text/HTML**
* **application/XML**
* **application/JSON**
* **application/x-www-form-urlencoded**
* **multipart/form-data**
* **custom**
* **none**

### Body

Add the data payload that will be sent in the request. The body structure will differ depending on the content type.

### Output Variable&#x20;

Save the response as a varaible. Example: `HTTPresult`

