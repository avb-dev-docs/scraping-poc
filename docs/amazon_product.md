# amazon_product Documentation

## Brief Description
The `amazon_product` object is designed to extract data from an Amazon product page for a given ASIN (Amazon's Product ID).

## Usage
This object is used to construct a query for retrieving product information from Amazon. It's typically used as part of a larger API system.

## Parameters
- `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character string consisting of uppercase letters and numbers.

## Return Value
The object doesn't return a value directly, but it's structured to be used in an API call that returns product information in JSON format.

## Examples

```javascript
// Example API request using the amazon_product object
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
- The ASIN must be exactly 10 characters long and consist only of uppercase letters and numbers.
- This object is designed to work with a specific API endpoint (https://api.webit.live/api/v1/realtime/ecommerce/amazon/product).
- The API response includes detailed product information such as price, availability, ratings, reviews, product features, and variations.
- Be aware of Amazon's terms of service regarding data scraping or API usage when implementing this in your projects.
- The object includes support for different Amazon domains (e.g., .com, .co.uk), but the default is set to the US store.