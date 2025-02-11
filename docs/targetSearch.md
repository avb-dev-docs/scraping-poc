# targetSearch Documentation

## Brief Description
targetSearch is a JSON object that defines the structure and parameters for performing a product search on Target's website.

## Usage
To use targetSearch, you need to send a POST request to the Target API endpoint with the required parameters. The targetSearch object defines the query structure and parsing options for this request.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of items to skip in the search results.
- `category` (string, optional): A 5-character alphanumeric category ID to filter results.
- `fulfillment` (enum, optional): Filter by fulfillment method. Options: "Pickup", "Shop in Store", "Same Day Delivery", "Shipping".
- `sort_by` (enum, optional): Sort order for results. Default is "Relevance". Other options include "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", "Newest".

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, rating, and image URLs.

## Examples

```javascript
// Example POST request
fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'iron flask'
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

## Notes or Considerations
- The API requires authentication. Make sure to include a valid authorization token in the request headers.
- The search results are paginated. Use the `offset` parameter to navigate through multiple pages of results.
- The API includes options for rendering and capturing network requests, which may affect response times.
- Be aware of rate limiting and other usage restrictions that may apply to the Target API.