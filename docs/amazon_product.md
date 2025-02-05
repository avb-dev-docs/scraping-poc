# amazon_product Documentation

## Brief Description
`amazon_product` is an object that facilitates data extraction from Amazon product pages using a given ASIN (Amazon's Product ID).

## Usage
To use `amazon_product`, you need to make a POST request to the specified endpoint with the required parameters. This object is designed to be used within an API environment.

## Parameters
- `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character alphanumeric string.

## Return Value
The `amazon_product` object returns a JSON response containing detailed information about the specified Amazon product, including:
- Product details (name, ASIN, parent ASIN, availability)
- Pricing information
- Ratings and reviews
- Product features and specifications
- Image URLs
- Available variations (size, color, etc.)

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
- Ensure you have the necessary API access and authentication token before making requests.
- The ASIN must be valid and correspond to an existing Amazon product.
- The data returned may vary depending on the product and its availability.
- Respect Amazon's terms of service and rate limits when using this API.
- The response includes detailed product information, which may be useful for various e-commerce applications, price tracking, or product analysis.