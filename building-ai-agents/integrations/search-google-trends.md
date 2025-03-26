---
description: Retrieve Google Trends keyword results in a MindStudio workflow
---

# Search Google Trends

## Sample Output

```json
{
  "search_metadata": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "status": "Success",
    "json_endpoint": "https://example.com/search/sample.json",
    "created_at": "2025-03-06 20:15:25 UTC",
    "processed_at": "2025-03-06 20:15:25 UTC",
    "google_trends_url": "https://example.com/trends",
    "raw_html_file": "https://example.com/search/sample.html",
    "prettify_html_file": "https://example.com/search/sample.prettify",
    "total_time_taken": 16.09
  },
  "search_parameters": {
    "engine": "google_trends",
    "q": "example_query",
    "hl": "en",
    "date": "today 12-m",
    "tz": "420",
    "data_type": "TIMESERIES"
  },
  "interest_over_time": {
    "timeline_data": [
      {
        "date": "Sample Date Range",
        "timestamp": "0000000000",
        "values": [
          {
            "query": "example_query",
            "value": "80",
            "extracted_value": 80
          }
        ]
      }
    ]
  }
}
```
