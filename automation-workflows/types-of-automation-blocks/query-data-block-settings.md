---
description: Configure these settings for the Query Data Source Block.
---

# Query Data Block Settings

## Query Data Source

1. From the **Data Source** drop-down menu, select which [Data Source](../../data-sources/what-is-a-data-source.md) to query. If you have not created a Data Source, select the **New** button to [create a new Data Source](../../data-sources/create-a-data-source.md).
2. In the **Variable Name** setting, enter the name of the [Variable](../../user-inputs-and-variables/what-is-a-variable.md) to save the Data Source query results.
3. In the **Max Results** setting, enter the maximum number of results to save from the Data Source query. The maximum number of results is 5. The default is 3.

## Query Template

In the **Query Template** setting, provide instructions on how the AI model should query the Data Source. Optionally reference Variables in the Data Source query by using double curly braces around the Variable name.

**Example:**

```
I am looking for information about {{topic}}.
```

Note that you can not leave the Query Template blank for the Block to function properly.

## Test the Data Source Query

1. Select the **Temperature** icon at the top of the Query Data Source Block.
2. In the **Query Tester** setting, enter a natural language query that optionally references Variables.
3. Select the **Send** icon in the Query Tester setting. Determine if the results are as you expect.

Note that uploading the file(s) DOES NOT mean the AI knows everything about your file(s). You must instruct the AI on how to query that file for the AI to use your Data Source properly.
