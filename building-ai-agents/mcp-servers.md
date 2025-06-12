---
description: Learn about creating an MCP server with MindStudio.
---

# MCP Servers

### What is an MCP Server?

An **MCP (Model Context Protocol) server** lets you expose one or more of your MindStudio agents as tools that external applications or LLMs can invoke. In practice, an MCP server:

* **Enables agents to work with external tools and data sources** without having to rebuild or redeploy them each time.
* Serves as a centralized endpoint that routes requests to any published agent you’ve added.

***

### How to Build an MCP Server with MindStudio



1.  **Configure Your Agent as a** [**Packaged Workflow**](packaged-workflows.md)

    * Open the editor of agent you want to expose and select the **Start** block.
    * Change the trigger type to **Packaged Workflow**.


2.  **Fill in Workflow Metadata**

    | Field                | Example Value                                    |
    | -------------------- | ------------------------------------------------ |
    | **Workflow ID/Name** | `Get AI News Scrape`                             |
    | **Description**      | `Get a bullet point summary of today’s AI news.` |
    | **Inputs**           | _(None—this workflow runs standalone)_           |
    | **Outputs**          | _One output: the summary string_                 |



3.  **Save and Publish**

    * Click **Save** to persist your changes.
    * Click **Publish** so the workflow is available in the workspace.


4.  **Copy Your Agent’s ID**

    * After publishing, the agent’s general settings will show its **Agent ID**.
    * Click the copy icon next to that ID


5.  **Create the MCP Server**

    * Navigate back to your main MindStudio workspace.
    * Select **MCP Server** from the Workspace settings dropdown.
    * Paste in your copied Agent ID in the space provided.
    * Tap **Add** to register this agent on the server.
    * Copy the connection details snippet to be used with your external integration.&#x20;



**Connection Details Example Snippet**

```json
{
  "mcpServers": {
    "mindstudio": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://v1.mindstudio-api.com/developer/mcp/v1/d21d0794-c547-421e-8c6b-4ed44b9d8c78",
        "--header",
        "Authorization: ${AUTH_TOKEN}",
        "--transport http-only"
      ],
      "env": {
        "AUTH_TOKEN": "Bearer sked835eff2eeb0609fce74096e6467c736365b59514ccc428d672dbed833562614e648d3c5051c25465d43289413a77e17177cbca890f8ea6652b234df130c6dc"
      }
    }
  }
}
```

***

### Integrating Your MCP Server with External Tools

* Copy the connection details snippet into the desired external application. This will vary depending on the service you are using.
  * [Claude](https://support.anthropic.com/en/articles/11175166-about-custom-integrations-using-remote-mcp)
  * [Open AI](https://platform.openai.com/docs/guides/tools-remote-mcp)
  * [Cursor](https://docs.cursor.com/context/model-context-protocol)

