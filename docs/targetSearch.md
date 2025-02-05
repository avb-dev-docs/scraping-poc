# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates product searches on Target's website, allowing users to extract data from Target search result pages.

## Usage
To use targetSearch, send a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target.
- `offset` (number, optional): The number of results to skip. Minimum value is 0.
- `category` (string, optional): Filter results by category. Must be a 5-character alphanumeric string.
- `fulfillment` (enum, optional): Filter by fulfillment method. Options: "Pickup", "Shop in Store", "Same Day Delivery", "Shipping".
- `sort_by` (enum, optional): Sort results. Default is "Relevance". Options include "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", "Newest".

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
- Ensure you have a valid API token for authentication.
- The API has a render option that simulates browser behavior, which may affect response times.
- Be mindful of Target's terms of service when using this API for data extraction.
- The API includes options for infinite scrolling and network capture, which may be useful for more comprehensive data collection.