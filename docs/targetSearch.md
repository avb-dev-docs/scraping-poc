# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website, providing a structured way to extract and parse search results.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters. The object handles the query building, rendering, and parsing of the search results.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip, used for pagination.
- `category` (string, optional): A 5-character alphanumeric code to filter results by category.
- `fulfillment` (enum, optional): Filter results by fulfillment method. Options include "Pickup", "Shop in Store", "Same Day Delivery", and "Shipping".
- `sort_by` (enum, optional): Sort the results. Options include "Relevance", "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", and "Newest".

## Return Value
The targetSearch object doesn't directly return a value, but it structures the API response. The response includes search results with details such as product name, brand, price, rating, and more.

## Examples

```javascript
// Basic search for "iron flask"
const searchRequest = {
  endpoint: "https://api.webit.live/api/v1/realtime/ecommerce/target/search",
  method: "POST",
  headers: {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  body: {
    query: "iron flask"
  }
};

// Search for headphones, sorted by price low to high
const searchRequest = {
  endpoint: "https://api.webit.live/api/v1/realtime/ecommerce/target/search",
  method: "POST",
  headers: {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  body: {
    query: "headphones",
    sort_by: "Price: Low to High"
  }
};
```

## Notes or Considerations
- Ensure you have the proper authorization token to make requests to the API.
- The search results are rendered and parsed using AI, which may affect response times.
- The API has a timeout of 60 seconds, so consider this when making requests with large result sets.
- Be mindful of rate limits and use the offset parameter for pagination when dealing with many results.
- The fulfillment and sort_by parameters use specific mappings, so refer to the documentation for the correct values.