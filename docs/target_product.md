# target_product Documentation

## Brief Description
`target_product` is an object that defines the query structure and parsing options for extracting product data from Target's website.

## Usage
This object is typically used as part of a larger system for web scraping or API integration with Target's product pages. It is not directly callable, but rather provides configuration for making requests to Target's product pages.

## Parameters
The `target_product` object expects one parameter in its query:

- `tcin` (string, required): The Target Commercial Item Number (TCIN) of the product. This should be an 8-digit string.

## Return Value
While `target_product` itself doesn't return a value, the system using this configuration will typically return a JSON object containing detailed product information from the Target website.

## Examples

1. Basic usage within a hypothetical API call:

```javascript
const api = new WebScrapingAPI(config);
const result = await api.scrape({
  ...target_product,
  variables: {
    tcin: "87973629"
  }
});
console.log(result);
```

2. Extracting specific product details:

```javascript
const productData = await fetchTargetProduct("79767634");
console.log(`Product Name: ${productData.product.name}`);
console.log(`Price: $${productData.product.price}`);
console.log(`Rating: ${productData.product.rating}`);
```

## Notes or Considerations

- This object is designed to work with Target's website structure as of the last update. Changes to Target's website may require updates to the query configuration.
- The `tcin` parameter must be a valid 8-digit Target product identifier.
- The scraping process includes a render step with specific timing and selectors, which may need adjustment based on Target's page load behavior.
- Be mindful of Target's terms of service and rate limiting when using this configuration for web scraping.
- The returned data structure is complex and includes detailed product information, images, pricing, and customer reviews. Familiarize yourself with the response format to effectively parse the data you need.