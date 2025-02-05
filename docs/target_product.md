# target_product Documentation

## Brief Description
target_product is an object that facilitates extracting product data from Target's website for a given product ID (TCIN).

## Usage
To use target_product, you need to make a POST request to the Target product endpoint with the required parameters.

## Parameters
- `tcin` (string, required): The Target product ID (TCIN) for the item you want to retrieve data for. Must be an 8-digit number.

## Return Value
Returns a JSON object containing detailed product information from the Target website.

## Examples

```javascript
// Example request
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/product', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    tcin: '87973629'
  })
});

const data = await response.json();
console.log(data);
```

## Notes or Considerations
- This object requires authentication. Make sure to include your API token in the request headers.
- The API has a rate limit. Be mindful of how frequently you make requests.
- Product data may change frequently. Consider implementing a caching strategy if you need to make multiple requests for the same product.
- Some product information may not be available for all items.