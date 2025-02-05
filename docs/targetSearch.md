# targetSearch Documentation

## Brief Description
The targetSearch API endpoint extracts data from Target search pages for given search keywords in real-time.

## Usage
This endpoint is designed to be used as part of the Nimble eCommerce API. To use it, send a POST request to the endpoint with the required parameters.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| query | string | Yes | The search term to use on Target |
| offset | number | No | Number of results to skip (min: 0) |
| category | string | No | Target category ID (5 alphanumeric characters) |
| fulfillment | enum | No | Fulfillment method (options: "Pickup", "Shop in Store", "Same Day Delivery", "Shipping") |
| sort_by | enum | No | Sorting method (default: "Relevance", options include "Featured", "Price: Low to High", etc.) |

## Return Value
The API returns a JSON object containing search results from Target, including product details such as name, brand, price, rating, and image URLs.

## Examples

### Python
```python
import requests

url = "https://api.webit.live/api/v1/realtime/ecommerce/target/search"
headers = {
    "Authorization": "Basic <YOUR_TOKEN>",
    "Content-Type": "application/json"
}
data = {
    "query": "iron flask"
}

response = requests.post(url, headers=headers, json=data)
print(response.json())
```

### JavaScript
```javascript
const axios = require('axios');

const url = 'https://api.webit.live/api/v1/realtime/ecommerce/target/search';
const headers = {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
};
const data = {
    query: 'iron flask'
};

axios.post(url, data, { headers })
    .then(response => console.log(response.data))
    .catch(error => console.error('Error:', error));
```

## Notes or Considerations
- Ensure you have the necessary authentication token before making requests.
- The API supports additional parameters for filtering and sorting results.
- Response times may vary depending on the complexity of the search and the number of results.
- Be aware of Target's terms of service when using this API for data extraction.