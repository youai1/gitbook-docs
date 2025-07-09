---
description: Query your own external database (postgres, mysql, supabase, etc.)
---

# Query Database

{% embed url="https://www.youtube.com/embed/eFb4O4LDg1s" %}

The Query Database block allows your AI Agent to connect to and query an external SQL database during runtime. It supports PostgreSQL, MySQL, and Microsoft SQL Server, making it ideal for workflows that require live data access — such as retrieving customer records, product inventory, or historical logs.

***

## Configurations

### Account

Connect the database account your agent will use to run queries.

You can choose:

* **Static Account:** A fixed database connection defined at build time.
* **Dynamic (Ask at Runtime):** Prompts the user to input database credentials during execution.

To connect, select your database type (PostgreSQL, MySQL, etc.) and enter:

| Info     | Example               |
| -------- | --------------------- |
| Host     | `db.abcd.supabase.co` |
| Port     | `5432`                |
| Database | `postgres`            |
| Username | `postgres`            |
| Password | _YOUR SECRET KEY_     |

***

### Query

Enter the SQL query to run against the external database. You can use dynamic variables with `{{brackets}}` to inject content from earlier in the workflow.

**Example (Static Query):**

```sql
SELECT * FROM users WHERE last_name = 'Williams';
```

**Example (Dynamic Query using variable):**

```sql
SELECT * FROM users WHERE last_name = '{{last_name}}';
```

{% hint style="info" %}
**Pro Tip:** You can use a [Generate Text Block](generate-text-block.md) to generate a query for you based on your natural language description. **Make sure to include Schema Info** when using AI-generated queries by providing table and column names to guide query generation.
{% endhint %}

***

### Output Format

Choose how the result should be returned. Options include:

* **JSON** (default): Structured data ideal for parsing or display.
* **CSV:** Comma-separated values, useful for exporting to spreadsheets or displaying flat tabular data.

***

### Output Variable

Set a variable name to store the query result. This variable can be used in later blocks to display results or make decisions.

**Example:**\
`query_result`

***

## How It Works

1. The block connects to the selected external database using the provided credentials.
2. The SQL query is executed (with variables substituted if used).
3. The result is returned in your chosen format and stored in the specified output variable.
4. The next block in your workflow can use this result to generate responses, make decisions, or display information.
