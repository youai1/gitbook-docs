---
description: Extract text content from a webpage
---

# Scrape URL Block

{% embed url="https://youtu.be/xcRdYpzAEf0" %}

The **Scrape URL Block** allows you to extract text content from a webpage and use it within your workflow. This block is ideal for gathering data dynamically from online sources to provide context for your AI Agents.

## **Configurations**

### **URL**

Provide the webpage URL you want to scrape. You can input a static URL directly or use a `{{variable}}` for dynamic URLs.

#### **Example**:

* Static: **`https://example.com/article`**
* Dynamic: **`{{inputURL}}`**

### **Output Variable**

Creates a new variable and saves the extracted text to it. Enter a `variable_name` to store the response for later use in the workflow.

### Auto-enhance

Automatically adjust settings for certain URLs to prevent scraping errors. In most cases, it is best to leave this enabled in order to ensure consistent scrape results.

### **Provider**

Select the scraping provider to process the webpage. Different providers will have different configuration settings and outputs. Choose the one that works best for your needs.

***

## Types of Providers for the Scrape URL Block

The **Scrape URL Block** supports multiple providers to extract webpage content, each offering different levels of customization and functionality.

### **Default**

The default provider is the best option for most web scraping tasks.

### **Firecrawl**

[Firecrawl](https://www.firecrawl.dev/) offers advanced configuration options for greater control over how webpages are scraped. You likely do not need to use Firecrawl, especially when auto-enhance is enabled. If you do choose to use Firecrawl, you have access to some additional options.

#### **Only Main Content**

When enabled, this setting returns only the main content of the page, such as the body text, while excluding headers, navigation bars, and footers. Disabling it includes the entire page content, including headers and sidebars.

#### **Include Screenshot**

When enabled, captures and returns a screenshot of the top of the page you are scraping. When disabled, it does not include a screenshot.

#### **Wait For**

Allows you to specify a delay (in milliseconds) before scraping begins to let the page fully load. By default, no wait time is applied. For example, setting it to **`500`** waits half a second before scraping.

#### **Absolute Paths**

Converts all relative paths in the scraped content to absolute URLs when enabled. This ensures that links and resources in the scraped content are fully qualified. When disabled, relative paths remain as they are.

#### **Headers**

Lets you include custom HTTP headers with your scraping request. This is useful for adding cookies, specifying a **`User-Agent`**, or passing authentication tokens.

#### **Remove Tags**

Allows you to define HTML tags to exclude from the scraped content. For instance, adding **`<footer>`** removes footer elements from the output.

***

## Best Practices

* **Validate URLs**: Ensure the URL points to a publicly accessible page with the desired content.
* **Monitor Structure Changes**: Webpages may change structure over time, which could affect scraping accuracy.
* **Use Variables**: Leverage dynamic variables to adapt the block to multiple use cases without manually changing the URL.
* **Set Clear Outputs**: Choose meaningful variable names to make workflow debugging and customization easier.
