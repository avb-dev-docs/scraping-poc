# target_product Documentation

## Brief Description
The target_product API endpoint extracts detailed product information from a Target product page for a given Target product ID (TCIN).

## Usage
This endpoint is accessed via a POST request to the Nimble eCommerce API. You need to provide the Target product ID (TCIN) as a parameter.

## Parameters

| Parameter | Type   | Required | Description                    |
|-----------|--------|----------|--------------------------------|
| tcin      | string | Yes      | Target's product ID (8 digits) |

JSON representation:
```json
{
  "tcin": "87973629"
}
```

## Prerequisites

| Prerequisite | Description |
|--------------|-------------|
| API Key      | Required for authentication |
| Content-Type | Set to application/json     |

## Return Value
The API returns a JSON object containing detailed product information, including name, brand, price, description, images, specifications, and customer reviews.

## Examples

### Python
```python
import requests

url = "https://api.webit.live/api/v1/realtime/ecommerce/target/product"
headers = {
    "Authorization": "Basic <YOUR_API_KEY>",
    "Content-Type": "application/json"
}
data = {
    "tcin": "87973629"
}

response = requests.post(url, headers=headers, json=data)
product_data = response.json()
print(product_data)
```

### JavaScript
```javascript
const axios = require('axios');

const url = 'https://api.webit.live/api/v1/realtime/ecommerce/target/product';
const headers = {
    'Authorization': 'Basic <YOUR_API_KEY>',
    'Content-Type': 'application/json'
};
const data = {
    tcin: '87973629'
};

axios.post(url, data, { headers })
    .then(response => {
        console.log(response.data);
    })
    .catch(error => {
        console.error('Error:', error);
    });
```

## Notes or Considerations
- Ensure you have a valid API key for authentication.
- The TCIN must be an 8-digit string.
- The API uses web scraping techniques, so be mindful of Target's website structure changes that might affect the response.
- Respect Target's terms of service and rate limits when using this API.