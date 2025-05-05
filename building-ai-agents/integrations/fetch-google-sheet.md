---
description: Retrieve content from a Google Sheet in a MindStudio workflow
---

# Fetch Google Sheet

{% embed url="https://www.youtube.com/embed/gYANwOaQGqY" %}

## Configuration

### Account&#x20;

#### Dynamic (Ask at runtime)

This setting will ask a user to login to their Google Drive account when they run the app.

#### Connect a New Account

Follow the instructions on the pop-up window to directly connect MindStudio to your Google Drive account.&#x20;

### Spreadsheet&#x20;

Add the spreadsheet URL for the Google sheet you want to fetch. If you have connected your Google Drive account, you can search for your spreadsheet by selecting the **search folder icon** next to the text field.&#x20;

This section can include variables.&#x20;

### Export Format

Select the format you want the spreadsheet exported as. Options include:

* **Comma-Seperated-Values (CSV)**
* **JSON (Google Sheet Format)**

### Range

Enter the range values that you want to fetch from the spreadsheet. Example: `Sheet1!A1:Z1000`

### Output Variable&#x20;

Save the contents of the fetched spreadsheet to a variable. Example: `Sheet_fetch_1`

## Sample Output - JSON

```json
{
  "range": "Testcases!A1:Z1015",
  "majorDimension": "ROWS",
  "values": [
    ["Lorem Ipsum Test", "Random Percentage:", "42.73%"],
    ["Dolor Sit", "Amet Consectetur", "Adipiscing Elit", "Status", "Notes", "Percentage"],
    ["Sed Do", "Eiusmod Tempor", "Incididunt Ut", "Passed"],
    ["", "Labore Et", "", "Pending"],
    ["", "Dolore Magna", "", "In Progress"],
    ["Aliqua Enim", "Ad Minim", "Veniam Quis", "Completed"],
    ["", "Nostrud Exercitation", "Ullamco Laboris", "Skipped"],
    ["", "Nisi Ut", "Aliquip Ex", "Blocked"],
    ["", "Ea Commodo", "Consequat Duis", "Passed"],
    ["Aute Irure", "Dolor In", "Reprehenderit In", "Failed"],
    ["", "Voluptate Velit", "Esse Cillum", "Passed"]
  ]
}
```

## Sample Output - CSV

```json
First Name,Last Name,Email,Phone Number,Address,City,State,Zip Code
John,Doe,example@example.com,123-456-7890,123 Main Street,Anytown,CA,12345
Jane,Smith,sample@example.com,987-654-3210,456 Oak Avenue,Somewhere,NY,67890
Michael,Johnson,placeholder@example.com,555-123-4567,789 Pine Road,Elsewhere,TX,54321
```
