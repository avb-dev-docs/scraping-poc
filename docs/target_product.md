# target_product Documentation

## Brief Description
The `target_product` object is used to extract detailed product information from a Target product page using a given Target product ID (TCIN).

## Usage
To use `target_product`, you need to make a POST request to the Target product endpoint with the required parameters.

## Parameters
- `tcin` (string, required): The Target product ID (TCIN) of the product you want to retrieve information for. Must be an 8-digit number.

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
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

## Notes or Considerations
- The API requires authentication. Make sure to replace `<TOKEN>` with your actual API token.
- The product information is scraped in real-time, so response times may vary depending on the target website's performance.
- The returned data includes various details such as product name, brand, price, description, images, specifications, and user ratings.
- Be mindful of Target's terms of service and usage limits when using this API.
- The API uses a render flow to ensure all dynamic content is loaded before scraping, which may increase response times but provides more comprehensive data.