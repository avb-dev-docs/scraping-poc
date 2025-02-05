# amazon_product Documentation

## Brief Description
`amazon_product` is an object that facilitates extracting data from an Amazon product page for a given ASIN (Amazon's Product ID).

## Usage
To use `amazon_product`, you need to make a POST request to the specified endpoint with the required parameters.

## Parameters
- `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character alphanumeric string.

## Return Value
The `amazon_product` object returns a JSON response containing detailed information about the requested Amazon product.

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
- The ASIN must be valid and correspond to an existing Amazon product.
- The response includes various details about the product, such as price, availability, ratings, and product variations.
- The API supports multiple domains (e.g., 'com', 'co.uk'), defaulting to the US domain.
- Be mindful of Amazon's terms of service when using this API to scrape product data.