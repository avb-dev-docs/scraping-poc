# targetSearch Documentation

## Brief Description

targetSearch is an object that facilitates searching for products on Target's website and extracting structured data from the search results.

## Usage

To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters. The object handles URL construction, request formatting, and response parsing.

## Parameters

- `query` (string, required): The search term to look for on Target.
- `offset` (number, optional): The number of results to skip, used for pagination.
- `category` (string, optional): A 5-character alphanumeric category code to filter results.
- `fulfillment` (string, optional): Filter by fulfillment method. Options are "Pickup", "Shop in Store", "Same Day Delivery", or "Shipping".
- `sort_by` (string, optional): Sort order for results. Default is "Relevance". Other options include "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", and "Newest".

## Return Value

The targetSearch object doesn't directly return a value, but it processes the API response to provide structured data about the search results, including product details like name, brand, price, rating, and image URLs.

## Examples

```javascript
// Basic search for "iron flask"
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'iron flask'
  })
});

const data = await response.json();
console.log(data.parsing.search_results);

// Search with additional parameters
const advancedResponse = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'headphones',
    fulfillment: 'Shipping',
    sort_by: 'Price: Low to High'
  })
});

const advancedData = await advancedResponse.json();
console.log(advancedData.parsing.search_results);
```

## Notes or Considerations

- The API requires authentication. Make sure to replace `<YOUR_TOKEN>` with your actual API token.
- The search results are paginated. Use the `offset` parameter to retrieve additional pages of results.
- The actual data structure of the response may be more complex than shown in the examples. Refer to the full API documentation for detailed response format.
- Be mindful of Target's terms of service and any rate limiting when using this API for frequent requests.