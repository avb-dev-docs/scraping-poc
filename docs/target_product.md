# target_product Documentation

## Brief Description
target_product is an object that facilitates retrieving product data from Target's website using a given Target product ID (TCIN).

## Usage
To use target_product, you need to make a POST request to the Target product endpoint with the required parameters.

## Parameters
- `tcin` (string, required): The Target product ID (TCIN), must be an 8-digit number.

## Return Value
The endpoint returns a JSON object containing detailed product information from Target.

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
.then(data => console.log(data));
```

## Notes or Considerations
- The API requires authentication. Make sure to include a valid authorization token in the request headers.
- The response includes various details about the product, such as name, brand, price, description, images, specifications, and customer ratings.
- The API uses web scraping techniques, so be mindful of Target's terms of service and rate limiting when making requests.
- The response time may vary depending on the complexity of the product page and network conditions.