# target_product Documentation

## Brief Description
`target_product` is a JSON object that defines the configuration for extracting product data from Target's website using a given Target product ID (TCIN).

## Usage
This object is typically used as part of a larger API or scraping system. It defines the query parameters, URL structure, and parsing options for retrieving product information from Target.com.

## Parameters
- `tcin` (string, required): The Target product ID, must be an 8-digit number.

## Return Value
The object doesn't return a value directly, but when used in an API call, it would return a JSON object containing detailed product information from Target.com.

## Examples

```javascript
// Example API call using the target_product configuration
const response = await api.query('target_product', {
  tcin: '87973629'
});

console.log(response.parsing.product.name);
// Output: "Mr. Coffee 12-Cup Programmable Coffee Maker - Black/Stainless Steel"
```

## Notes or Considerations
- This object is designed to work with a specific API or scraping system that understands its structure.
- The actual data retrieval and parsing are handled by external systems defined in the `parseOptions` and `renderOptions`.
- Be mindful of Target's terms of service when using this for web scraping.
- The `render` option is set to true, which may indicate that JavaScript rendering is required to fully extract the product data.
- There's a built-in delay in the `render_flow`, which may affect the speed of data retrieval.