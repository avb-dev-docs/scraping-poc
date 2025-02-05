# target_product Documentation

## Brief Description
`target_product` is an object that facilitates extracting product data from Target product pages using a given Target product ID (TCIN).

## Usage
To use `target_product`, you need to make a POST request to the Target product endpoint with the required parameters.

## Parameters
- `tcin` (string, required): The Target product ID (TCIN) of the item you want to retrieve information for. Must be an 8-digit number.

## Return Value
The `target_product` object returns a JSON response containing detailed product information from the Target product page.

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
- Ensure you have the necessary authentication token to make requests to the API.
- The API has a render option enabled, which may affect response times.
- The response includes various details about the product, such as name, brand, price, description, images, specifications, and customer ratings.
- Be aware of any rate limiting or usage restrictions when making requests to the API.