# amazon_product Documentation

## Brief Description
The `amazon_product` object is designed to extract data from an Amazon product page for a given ASIN (Amazon's Product ID).

## Usage
To use the `amazon_product` object, you need to make a POST request to the specified endpoint with the required parameters.

## Parameters
- `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character string containing only uppercase letters and numbers.

## Return Value
The `amazon_product` object returns a JSON response containing detailed information about the specified Amazon product.

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
- Ensure you have the necessary authorization token to make requests to the API.
- The ASIN must be exactly 10 characters long and contain only uppercase letters and numbers.
- The response includes detailed product information such as price, availability, product name, features, and variations.
- The API supports multiple domains (e.g., "com", "co.uk") for different Amazon marketplaces.
- Be aware of Amazon's terms of service and usage policies when scraping their website.