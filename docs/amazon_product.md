# amazon_product Documentation

## Brief Description
The `amazon_product` object is designed to extract data from an Amazon product page for a given ASIN (Amazon's Product ID).

## Usage
This object is used to construct API requests for retrieving Amazon product data. It defines the structure and parameters needed to make a successful API call.

## Parameters
- `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character alphanumeric string.

## Return Value
The object doesn't return a value directly, but it defines the structure of the API response, which includes detailed product information.

## Examples

```javascript
// Example API request
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/amazon/product', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    asin: 'B0C4ZZBD71'
  })
});

const data = await response.json();
console.log(data);
```

## Notes or Considerations
- The API requires authentication. Ensure you have the proper authorization token.
- The response includes extensive product details such as price, ratings, features, and variations.
- The object supports multiple domains (e.g., 'com', 'co.uk'), defaulting to the US store.
- Ensure the ASIN provided is valid to get accurate results.