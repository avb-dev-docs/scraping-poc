# target_product Documentation

## Brief Description
The `target_product` object is used to extract detailed product information from a Target product page using a given Target Composite Item Number (TCIN).

## Usage
To use the `target_product` object, you need to make a POST request to the Target product endpoint with the required TCIN.

## Parameters
- `tcin` (string, required): The Target Composite Item Number (TCIN) of the product. Must be an 8-digit number.

## Return Value
The `target_product` object returns a JSON response containing detailed information about the specified product, including name, brand, price, description, images, specifications, and customer ratings.

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
- The API requires authentication. Make sure to include a valid authorization token in the request headers.
- The product page is rendered before data extraction, which may increase response time.
- The API captures network requests containing "/web/pdp_client_v1" for additional data extraction.
- Ensure that the TCIN provided is valid and corresponds to an existing Target product.
- The response includes various details about the product, such as price, description, images, specifications, and customer ratings. Parse the response carefully to extract the information you need.
- Be aware of Target's terms of service and usage limits when using this API.