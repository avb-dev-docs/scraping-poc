# target_product Documentation

## Brief Description
`target_product` is an object that facilitates extracting product data from Target's website for a given product ID (TCIN).

## Usage
To use `target_product`, you need to make a POST request to the Target product API endpoint with the required parameters.

## Parameters
- `tcin` (string, required): Target's product ID (TCIN). Must be an 8-digit number.

## Return Value
Returns a JSON object containing detailed product information from Target's website.

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
- Ensure you have the necessary API access and authorization token before making requests.
- The API uses a rendering process to capture dynamic content, which may affect response times.
- Be mindful of Target's terms of service and any rate limiting when using this API.
- The returned data structure may change based on the specific product and availability of information on Target's website.