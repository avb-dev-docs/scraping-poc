# target_product Documentation

## Brief Description
`target_product` is an object that defines a query builder for extracting data from Target product pages using a given Target product ID (TCIN).

## Usage
The `target_product` object is used to construct API requests for retrieving detailed product information from Target's website. It specifies the URL structure, required parameters, and parsing options for the API call.

## Parameters
- `tcin` (string, required): The Target product ID, must be an 8-digit number.

## Return Value
The query builder doesn't return a value directly, but when used with an API, it will return a JSON object containing detailed product information.

## Examples

```javascript
// Example API request using the target_product query builder
const response = await api.query('target_product', {
  tcin: '87973629'
});

// The response will contain detailed product information
console.log(response.parsing.product.name);
console.log(response.parsing.product.price);
```

## Notes or Considerations
- This query builder is designed to work with a specific API (likely internal or proprietary).
- The API requires authentication, as indicated by the `Authorization` header in the example request.
- The query includes a render step, which may increase response time but ensures more accurate data extraction.
- The product data is extracted using a custom parser (parsit-ai) with a specific parser ID.
- Be aware of Target's terms of service and any rate limiting when using this API in production environments.