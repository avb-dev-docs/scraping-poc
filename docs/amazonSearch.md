# amazonSearch Documentation

## Overview

The amazonSearch API endpoint is designed to extract data from Amazon search results pages for a given search keyword. It provides real-time access to product information displayed on Amazon's search pages.

## Parameters

| Parameter | Type   | Required | Description                     |
|-----------|--------|----------|---------------------------------|
| query     | string | Yes      | The search keyword or phrase    |

## JSON Representation

```json
{
  "query": "string"
}
```

## Prerequisites

| Requirement | Description |
|-------------|-------------|
| API Key     | A valid API key for authentication |
| API Access  | Approved access to the Nimble eCommerce API |

## Code Examples

### Python

```python
import requests

url = "https://api.webit.live/api/v1/realtime/ecommerce/amazon/search"
headers = {
    "Authorization": "Basic <YOUR_API_KEY>",
    "Content-Type": "application/json"
}
payload = {
    "query": "ironflask"
}

response = requests.post(url, json=payload, headers=headers)
data = response.json()
print(data)
```

### JavaScript

```javascript
const axios = require('axios');

const url = 'https://api.webit.live/api/v1/realtime/ecommerce/amazon/search';
const headers = {
  'Authorization': 'Basic <YOUR_API_KEY>',
  'Content-Type': 'application/json'
};
const payload = {
  query: 'ironflask'
};

axios.post(url, payload, { headers })
  .then(response => console.log(response.data))
  .catch(error => console.error('Error:', error));
```

## Response

The API returns a JSON object containing the search results. Key information includes:

- Product ASIN
- Product name
- Price
- Rating
- Number of reviews
- Image URL
- Product URL

For a detailed example of the response structure, please refer to the Example Response section in the API documentation.

## Notes and Considerations

- Ensure your API key has the necessary permissions to access this endpoint.
- Be mindful of rate limits and usage restrictions as per your API agreement.
- The search results may vary based on Amazon's current layout and available data.
- This API is designed for real-time data extraction and should not be used for bulk scraping.