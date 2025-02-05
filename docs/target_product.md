# target_product Documentation

## Brief Description
target_product is an object that facilitates extracting product data from Target's website for a given product ID (TCIN).

## Usage
To use target_product, you need to make a POST request to the Target product endpoint with the required parameters.

## Parameters
- `tcin` (string, required): The Target product ID (TCIN). Must be an 8-digit number.

## Return Value
Returns a JSON object containing detailed product information from the Target website.

## Examples

```javascript
// Example request
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/product', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    tcin: '87973629'
  })
});

const data = await response.json();
console.log(data);
```

## Notes or Considerations
- The API requires authentication. Make sure to replace `<YOUR_TOKEN>` with your actual API token.
- The response includes various details about the product, such as name, brand, price, description, images, specifications, and customer reviews.
- The API uses web scraping techniques, so be aware of potential rate limiting or changes to Target's website structure that could affect the results.
- Processing time may vary depending on the complexity of the product page and current server load.