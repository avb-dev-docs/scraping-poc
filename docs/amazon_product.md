# amazon\_product Documentation

## Brief Description

The `amazon_product` object is a JSON configuration used to extract data from an Amazon product page for a given ASIN (Amazon's Product ID).

## Usage

This object is typically used as part of an API request to retrieve detailed information about a specific Amazon product. It defines the structure for both the request and the expected response.

## Parameters

* `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character alphanumeric string.

## Return Value

The `amazon_product` object doesn't return a value directly, but it defines the structure of the API response, which includes detailed product information.

## Examples

```javascript
// Example API request
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
.then(data => console.log(data));
```

## Notes or Considerations

* The API requires authentication. Ensure you have a valid token before making requests.

* The response includes detailed product information such as price, availability, ratings, and product variations.

* The object supports multiple domains (e.g., "com", "co.uk"), allowing for region-specific product lookups.

* Be aware of Amazon's terms of service and usage policies when using this API to fetch product data.
