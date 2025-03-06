---
description: Retrieve content from a Google Sheet in a MindStudio workflow
---

# Fetch Google Sheet

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
