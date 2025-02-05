# target_product Documentation

## Brief Description
`target_product` is an object that defines the query structure and parameters for extracting product data from Target's website.

## Usage
This object is typically used as part of a larger API or system for scraping product information from Target. It's not meant to be used directly by end users, but rather as a configuration for web scraping tools or services.

## Parameters
The `target_product` object expects one required parameter:

- `tcin` (string, required): The Target Commercial Item Number (TCIN) of the product. This should be an 8-digit number.

## Return Value
While `target_product` itself doesn't return a value, it defines the structure for an API response containing detailed product information from Target.

## Examples

1. Basic usage within an API call:

```javascript
const productData = await fetchTargetProduct({
  tcin: "87973629"
});
```

2. Extracting specific product details:

```javascript
const { name, brand, price, rating } = productData.parsing.product;
console.log(`${name} by ${brand} - $${price} (${rating} stars)`);
```

## Notes or Considerations

- This object is designed for use with specific web scraping or API tools and may not work as a standalone function.
- The TCIN must be exactly 8 digits long.
- The scraping process involves rendering the page and waiting for specific elements, which may take some time.
- Be aware of Target's terms of service and legal considerations when scraping their website.
- The returned data structure is complex and may require careful parsing to extract desired information.
- This tool is designed to work with Target's US website only.