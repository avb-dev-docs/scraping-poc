# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant data from the search results.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip, useful for pagination.
- `category` (string, optional): A 5-character alphanumeric code to filter results by category.
- `fulfillment` (enum, optional): Filter results by fulfillment method. Options are "Pickup", "Shop in Store", "Same Day Delivery", or "Shipping".
- `sort_by` (enum, optional): Sort the results. Options include "Relevance", "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", and "Newest".

## Return Value
targetSearch returns a JSON object containing the search results, including product details such as name, brand, price, rating, and image URLs.

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
```

```javascript
// Search for "headphones" with sorting and fulfillment options
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'headphones',
    sort_by: 'Price: Low to High',
    fulfillment: 'Shipping'
  })
});

const data = await response.json();
console.log(data.parsing.search_results);
```

## Notes or Considerations
- Ensure you have a valid API token for authentication.
- The API has a render flow that includes waiting for certain elements and performing actions like infinite scrolling. This may affect response times.
- The search results are parsed using an AI-based parser, which may occasionally result in inconsistencies in the extracted data.
- Be mindful of Target's terms of service and rate limits when using this API for frequent requests.