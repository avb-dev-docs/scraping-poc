# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting structured data from the search results.

## Usage
To use targetSearch, make a POST request to the Target search API endpoint with the required parameters. The object handles URL construction, parameter validation, and result parsing.

## Parameters
- `query` (string, required): The search term to look for on Target.
- `offset` (number, optional): The number of results to skip, used for pagination.
- `category` (string, optional): A 5-character alphanumeric category code to filter results.
- `fulfillment` (enum, optional): Filter by fulfillment method. Options: "Pickup", "Shop in Store", "Same Day Delivery", "Shipping".
- `sort_by` (enum, optional): Sort results. Default is "Relevance". Other options include "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", "Newest".

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, image URL, and more for each item found.

## Examples

```javascript
// Basic search for "iron flask"
{
  "endpoint": "https://api.webit.live/api/v1/realtime/ecommerce/target/search",
  "method": "POST",
  "headers": {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  "body": {
    "query": "iron flask"
  }
}

// Search for headphones, sorted by price low to high
{
  "endpoint": "https://api.webit.live/api/v1/realtime/ecommerce/target/search",
  "method": "POST",
  "headers": {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  "body": {
    "query": "headphones",
    "sort_by": "Price: Low to High"
  }
}
```

## Notes or Considerations
- Ensure you have proper authorization to use the API.
- The API uses server-side rendering and may have a longer response time due to additional processing.
- Results may include sponsored items, which are marked in the response.
- Be mindful of rate limits and use the offset parameter for pagination when dealing with large result sets.