---
description: Execute custom code in your AI workflow
---

# Custom Workflow Functions

**Functions** in MindStudio empower you to extend the capabilities of your workflows by running JavaScript or Python code directly within your automation. Functions are created within the Editor and are executed in a workflow via the Run Function Block.

When working with the **Function Tab** in MindStudio, the interface is designed to to write and test code, and support supporting dynamic inputs, configurations, and debugging features to ensure smooth execution.

## Create a New Function

There are two primary ways to create a new function in MindStudio. Both approaches will create a new function in your Functions Folder, and open a blank function editor where you can specify the environment, write your code, configure inputs, and test the function.

#### From the Explorer

1. Navigate to the **Explorer** panel on the left-hand side of the editor.
2. Hover over the **Functions** folder.
3. Click the **+** button or right-click and select **New Function**.
4. A new function tab will open where you can begin writing your custom code.

#### From the Run Function Block

1. Add a **Run Function Block** to your workflow.
2. In the block configuration, click **New...** to create a new function.
3. A new function tab will open, allowing you to define and configure the function.

***

## Function Setup

Functions in MindStudio can be written in either JavaScript or Python, giving you flexibility to choose the language that best suits your needs. The function editor provides a modern development environment with syntax highlighting, auto-completion, and real-time error checking.

{% stepper %}
{% step %}
### Configure Function Details

These details are displayed in the **Function Details** panel on the right. Provide a **Name** and optional **Description** for your function. Then select the programming environment for your function: **JavaScript** (Node.js) or **Python**.

{% hint style="info" %}
**Note:** For Python functions, you can import external libraries to extend functionality.
{% endhint %}
{% endstep %}

{% step %}
### Write the Function

Use the **Code Tab** to write the logic for your function. Utilize the available methods (see reference table below) to integrate your function seamlessly with configurations.
{% endstep %}

{% step %}
### (Optional) Create Configurations

Use the **Configurations Tab** to define JSON for customizable settings that users can modify when implementing your function in their workflows. These settings can include input fields, drop-downs, toggles, and other UI elements that make your function more flexible and user-friendly.
{% endstep %}
{% endstepper %}

## Code Tab

The **Code Tab** is the central workspace for writing the logic of your function. Here, you can write code in either JavaScript or Python, depending on the selected environment. The editor features syntax highlighting, making the code more readable and easier to debug.

### Available Methods

**`ai.config`** – Object containing configuration variables defined in MindStudio

**`ai.vars`** – Object containing runtime variables defined by other functions or blocks.

**`ai.getConfig(variableName)`** – Return the value of a configuration variable. If the configuration variable resolves to a runtime variable, resolve that value before returning

**`ai.log(value)`** – Update the progress text for the user. If your function takes a long time to run, this can be helpful in communicating what is happening to the user.

**`ai.scrapeUrl(url)`** – Scrape the contents of a URL and return an object containing the text extracted from the page, the raw HTML, and some structured metadata (page title, description, resolved URL, thumbnail image URL).

**`ai.searchGoogle(query)`** – Search Google for a query and return the first page of results. Returns an object containing all the results as a block of text, as well as individually as an array of objects containing the title, description, and URL for each result.

**`ai.queryDataSource(dataSourceId, query, numResults)`** – Perform a query against a data source defined in a project. Returns a string result. If `numResults` is not provided, only one chunk will be returned.

**`ai.uploadFile(body)`**– Upload a file and return a URL. File must be a valid Base 64 data URL.

**`ai.crmLog(value)`**– For apps with logging enabled, log a value to the app's user logs.

## Configuration Tab

The **Configuration Tab** enables developers to define a configuration JSON file for their function. This JSON allows you to set up customizable settings, such as text inputs, drop-downs, or other UI elements, that non-technical users can configure with when they add the function to the **Run Function Block** in workflows.

### Configuration JSON Structure

{% code fullWidth="false" %}
```json
config = {
	thumbnailUrl: "URL" 
	//(Optional) Reference image used in the Community Functions menu.
	
	blockStyle: { 
	//(Optional) Used to override default Automation Canvas block styles 
	
		backgroundImageUrl: "URL",  
		//Displays an image as the background of the block. Overrides background color.
		
		backgroundColor: "#HEXCOD",
		//Defines the background color of the block. Requires a hexcode or HTML color name
		
		foregroundColor: "#HEXCOD",
		//Defines the color of the label text. Requires a hexcode or HTML color name
		
		label: "BLOCK NAME"
		//Sets the text label string 
	},
	
	configurationSections: [
	//(Optional) Creates configuration fields for the block. These are the settings that someone fills in on the right hand panel in the Automation Canvas
	
		{
			"title": "HEADER LABEL",
			//Defines the string for the section title
			
			"items": [
			//Each item object is an individual UI element added to config settings
				{
					"label": "LABEL TEXT", 
					//Defines item label
					
					"variable": "VARIABLE_NAME",
					//Assigns value to a variable for use in the Code Tab.
					
					"type": "INPUT TYPE"
					//Defines the input type.
						//"text" = Form field
						//"secret" = Form field with hidden text. Does not transfer on remix.
						//"select" = Dropdown menu
						//"map" = Creates input for key:value pairs
						//"dataSource" = Dropdown menu to select a data source
					
					selectOptions: [
					//Only use when using "select" input type.
						{
							label: "OPTION 1"
							value: "VALUE TO ASSIGN"
						},
						{
							label: "OPTION 2"
							value: "VALUE TO ASSIGN"
						}
					],
					
					helpText: "STRING"
					//Defines helper text that appears under the input.
					
					textOptions: {
						textType: "TYPE"
							//Resizes form field. 
								//"default" = single line
								//"multiline" = textarea
					}
				}
			],
		}
	]
}
```
{% endcode %}

## Test Data Tab

The **Test Data Tab** is a dedicated space for verifying the behavior of your function with predefined inputs. You can simulate runtime variables such as `ai.vars` and `ai.config` by defining mock data to test different scenarios. This feature allows you to ensure that your function behaves as expected without needing to integrate it into a full workflow.

## Right Hand Panel Controls

### **Function Details Panel**

Displays key information about your function. Here, you can set the function’s name and description, which will be used to identify it in the **Run Function Block**. You can also select the environment—either JavaScript (Node.js) or Python—for your function.

Note: If you choose Python, you have the added flexibility of importing external libraries to extend functionality. The panel also displays the current configuration and runtime variables available for testing.

### Configuration Preview

Live preview of the configuration interface, giving you immediate feedback on how your JSON structure set the Configuration Tab will appear to users when they edit the block.

### Quick Help Tab

Built-in reference guide. Displays the guide relevant to what you are editing.