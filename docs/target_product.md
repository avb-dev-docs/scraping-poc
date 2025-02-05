# target_product Documentation

## Brief Description
The `target_product` object is used to extract detailed product information from a Target product page using a given TCIN (Target's Product ID).

## Usage
To use `target_product`, you need to make a POST request to the Target product API endpoint with the required parameters.

## Parameters
- `tcin` (string, required): The Target product ID (TCIN) of the item you want to retrieve information for. Must be an 8-digit number.

## Return Value
Returns a JSON object containing detailed product information including name, brand, price, description, images, specifications, and customer reviews.

## Examples

```javascript
// Example POST request
fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/product', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    tcin: '87973629'
  })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

## Notes or Considerations
- You need a valid API token to access the Target product API.
- The API has a render functionality that waits for certain elements to load before scraping the data, which may affect response times.
- The response includes various details about the product, including pricing, images, specifications, and customer reviews.
- Be aware of Target's terms of service and usage limits when using this API.