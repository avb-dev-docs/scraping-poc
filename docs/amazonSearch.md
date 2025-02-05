# amazonSearch Documentation

## Overview

The amazonSearch API endpoint is designed to extract data from Amazon search result pages for a given search keyword in real-time.

## Required Parameters

| Parameter | Type   | Description                    |
|-----------|--------|--------------------------------|
| query     | string | The search keyword or phrase   |

## JSON Representation

```json
{
  "query": "string"
}
```

## Prerequisites

| Prerequisite | Description |
|--------------|-------------|
| API Key      | A valid API key for authentication |
| Account      | An active account with the API service |

## Code Examples

### Python

```python
import requests
import json

url = "https://api.webit.live/api/v1/realtime/ecommerce/amazon/search"
headers = {
    "Authorization": "Basic <YOUR_API_KEY>",
    "Content-Type": "application/json"
}
data = {
    "query": "ironflask"
}

response = requests.post(url, headers=headers, data=json.dumps(data))
results = response.json()
print(results)
```

### JavaScript

```javascript
const axios = require('axios');

const url = 'https://api.webit.live/api/v1/realtime/ecommerce/amazon/search';
const headers = {
    'Authorization': 'Basic <YOUR_API_KEY>',
    'Content-Type': 'application/json'
};
const data = {
    query: 'ironflask'
};

axios.post(url, data, { headers })
    .then(response => {
        console.log(response.data);
    })
    .catch(error => {
        console.error('Error:', error);
    });
```

## Response Format

The API returns a JSON object containing the search results. Each result includes details such as:

- ASIN (Amazon Standard Identification Number)
- Product name
- Price
- Rating
- Number of reviews
- Product URL
- Image URL

## Notes and Considerations

- Ensure you have the necessary permissions and comply with Amazon's terms of service when using this API.
- The API uses a parser with ID "6666fbe64acb2423809a0abb" for extracting data from the search results page.
- The default country is set to "US", but the API supports both "com" and "co.uk" domains.
- Rate limiting may apply, so consider implementing appropriate delays between requests for large-scale scraping.