# Custom Function Methods

### Extensions

#### `scrapeUrl(url: string, scrapeSettings?: object): Promise<string>`

Scrapes metadata or content from the specified URL using optional custom settings.

**Parameters**

| Name             | Type     | Description                                |
| ---------------- | -------- | ------------------------------------------ |
| `url`            | `string` | URL to scrape.                             |
| `scrapeSettings` | `object` | _(optional)_ Custom settings for scraping. |

**Returns**

`Promise<string>` — JSON‑stringified scrape result.

***

#### `searchGoogle(query: string): Promise<string>`

Performs a Google web search and returns relevant results.

**Parameters**

* `query` (`string`): Search query string.

**Returns**

`Promise<string>` — JSON‑stringified list of results.

***

#### `rehostImage(imageUrl: string): Promise<string>`

Downloads and re‑hosts an image to a secure internal location.

**Parameters**

* `imageUrl` (`string`): Public URL of the image.

**Returns**

`Promise<string>` — JSON‑stringified object containing the new hosted image URL.

***

#### `concatenateAudio(urls: string[], options: object): Promise<string>`

Merges multiple audio files (e.g., MP3, WAV) into a single audio stream.

**Parameters**

| Name      | Type       | Description                              |
| --------- | ---------- | ---------------------------------------- |
| `urls`    | `string[]` | Array of audio file URLs.                |
| `options` | `object`   | Settings (e.g., fade in, output format). |

**Returns**

`Promise<string>` — JSON‑stringified result (e.g., output URL or metadata).

***

#### `unzipFile(zipUrl: string): Promise<string>`

Unzips a `.zip` file from the given URL and returns its contents or links.

**Parameters**

* `zipUrl` (`string`): URL to a zip archive.

**Returns**

`Promise<string>` — JSON‑stringified file tree or extracted file URLs.

***

#### `analyzeImage(imageUrl: string, prompt: string): Promise<string>`

Performs visual analysis of an image using a textual prompt.

**Parameters**

| Name       | Type     | Description                              |
| ---------- | -------- | ---------------------------------------- |
| `imageUrl` | `string` | URL of the image to analyze.             |
| `prompt`   | `string` | Instruction or question about the image. |

**Returns**

`Promise<string>` — JSON‑stringified analysis result.

***

#### `searchGoogleImages(query: string): Promise<string>`

Fetches relevant images based on a search query.

**Parameters**

* `query` (`string`): Image search keywords.

**Returns**

`Promise<string>` — JSON‑stringified array of image URLs or metadata.

***

#### `generateChart(data: object, width?: number, height?: number, backgroundColor?: string): Promise<string>`

Generates a chart image from structured data.

**Parameters**

| Name              | Type     | Description                                        |
| ----------------- | -------- | -------------------------------------------------- |
| `data`            | `object` | Chart data and configuration.                      |
| `width`           | `number` | _(optional)_ Image width in pixels (default 500).  |
| `height`          | `number` | _(optional)_ Image height in pixels (default 300). |
| `backgroundColor` | `string` | _(optional)_ Background color (default white).     |

**Returns**

`Promise<string>` — Base64‑encoded chart image or URL.

***

#### `queryDataSource(dataSourceId: string, query: string, numResults?: number): Promise<string>`

Executes a query against a configured data source (e.g., SQL, vector DB).

**Parameters**

| Name           | Type     | Description                                     |
| -------------- | -------- | ----------------------------------------------- |
| `dataSourceId` | `string` | Target data source identifier.                  |
| `query`        | `string` | Query string to execute.                        |
| `numResults`   | `number` | _(optional)_ Max number of results (default 1). |

**Returns**

`Promise<string>` — JSON‑stringified query results.

***

#### `uploadFile(body: string, contentType: string, encoding: BufferEncoding): Promise<{ url: string }>`

Uploads a file and returns its hosted URL.

**Parameters**

| Name          | Type             | Description                             |
| ------------- | ---------------- | --------------------------------------- |
| `body`        | `string`         | File contents (base64‐encoded or text). |
| `contentType` | `string`         | MIME type of the file.                  |
| `encoding`    | `BufferEncoding` | Encoding format used.                   |

**Returns**

`Promise<{ url: string }>` — Object containing the hosted file URL.

***

#### `log(value: string): void`

Sends a log message to the workflow execution log.

**Parameters**

* `value` (`string`): Message to log.

**Returns**

`void`

***

#### `generateImage(prompt: string, modelId: string): Promise<{ b64_json: string }>`

Generates an image from a text prompt using a specified model.

**Parameters**

| Name      | Type     | Description                         |
| --------- | -------- | ----------------------------------- |
| `prompt`  | `string` | Text prompt for image generation.   |
| `modelId` | `string` | Identifier of the generation model. |

**Returns**

`Promise<{ b64_json: string }>` — Base64‑encoded image payload.&#x20;
