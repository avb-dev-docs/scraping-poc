# target_product Documentation

## Brief Description
`target_product` is an object that facilitates extracting product data from Target's website for a given product ID (TCIN).

## Usage
To use `target_product`, you need to make a POST request to the Target product endpoint with the required parameters.

## Parameters
- `tcin` (string, required): Target's unique product identifier (TCIN). Must be an 8-digit number.

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
.then(data => console.log(data));
```

## Notes or Considerations
- Ensure you have proper authorization to access the API endpoint.
- The API uses a render flow to capture dynamic content, which may increase response time.
- Product data is extracted using an AI-powered parser, so results may vary based on the target webpage's structure.
- Be mindful of Target's website terms of service when using this API.