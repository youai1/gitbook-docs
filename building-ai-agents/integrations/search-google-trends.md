---
description: Retrieve Google Trends keyword results in a MindStudio workflow
---

# Search Google Trends

## Configuration

### Query&#x20;

Type in the text queries you want to send. Make sure each query is separated by a comma. Example: `coffee,pizza,dark chocolate`.

The search query can include variables.&#x20;

### Output Variable&#x20;

Specify the name of the output variable that will store the results. Example: `Trends_result`

### Advanced Settings&#x20;

#### Data Type

Specify the type of search you want to make. The following options are:

* `Interest over time (TIMESERIES)`
* `Breakdown by Region`
* `Interest by Region (GEO_MAP_0)`
* `Related Topics`
* `Related Queries`

#### Category&#x20;

This parameter is used to define the search category. By default this parameter is set to `0` which defines `All Categories`. You can see the full list of parameters [here.](https://serpapi.com/google-trends-categories)

#### Language&#x20;

Define the language parameter. The default is set to `en` for English. See the full list of parameters [here.](https://serpapi.com/google-languages)

#### Location&#x20;

This parameter defines the location from where you want the search to originate. The default is set to Worldwide. You can see the full list of parameters [here.](https://serpapi.com/google-trends-locations)&#x20;

#### Date&#x20;

Specify the date range of the trends you are searching. Available parameters to define a date include:

* `now 1-H` - Past hour
* `now 4-H` - Past 4 hours
* `now 1-d` - Past day
* `now 7-d` - Past 7 days
* `today 1-m` - Past 30 days
* `today 3-m` - Past 90 days
* `today 12-m` - Past 12 months
* `today 5-y` - Past 5 years
* `all` - 2004 - present

You can also pass custom values by using `yyyy-mm-dd yyyy-mm-dd`

#### Time Offset&#x20;

This parameter is used to define the timezone. The default timezone is set to `420` (Pacific Day Time (PDT): -07:00). Value is shown in minutes and can span from `-1439` to `1439`.

Other Timezone examples:\
`420` - PDT\
`600` - Pacific/Tahiti\
`-540` - Asia/Tokyo\
`-480` - Canada/Pacific.

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
