# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product information.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of items to skip in the search results.
- `category` (string, optional): A specific category ID to filter the search results.
- `fulfillment` (string, optional): Filter by fulfillment method (e.g., "Pickup", "Shipping").
- `sort_by` (string, optional): Sort the results (e.g., "Relevance", "Price: Low to High").

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, rating, and image URLs.

## Examples

```javascript
// Basic search
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'iron flask'
  })
});

// Search with additional parameters
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'headphones',
    fulfillment: 'Shipping',
    sort_by: 'Price: Low to High'
  })
});
```

## Notes or Considerations
- The API requires authentication. Make sure to include a valid authorization token in the request headers.
- The search results may be paginated. Use the `offset` parameter to navigate through multiple pages of results.
- Some parameters like `fulfillment` and `sort_by` have specific allowed values. Refer to the API documentation for the complete list of options.
- The API includes a rendering process that may take some time. Consider implementing appropriate timeout handling in your application.