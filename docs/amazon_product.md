# amazon_product Documentation

## Brief Description
amazon_product is an object that facilitates extracting product data from Amazon product pages using a given ASIN (Amazon Standard Identification Number).

## Usage
To use amazon_product, you need to make a POST request to the specified endpoint with the required parameters.

## Parameters
- `asin` (string, required): The 10-character ASIN of the Amazon product. Must match the pattern ^[A-Z0-9]{10}$.

## Return Value
The object returns a JSON response containing detailed product information extracted from the Amazon product page.

## Examples

```javascript
// Example POST request
fetch('https://api.webit.live/api/v1/realtime/ecommerce/amazon/product', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    asin: 'B0C4ZZBD71'
  })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

## Notes or Considerations
- Ensure you have the necessary authorization token to access the API.
- The ASIN must be a valid 10-character string containing only uppercase letters and numbers.
- The response includes detailed product information such as price, availability, ratings, reviews, features, and variations.
- The API supports multiple domains (e.g., "com", "co.uk") for different Amazon marketplaces.
- Be mindful of Amazon's terms of service and usage policies when using this API.