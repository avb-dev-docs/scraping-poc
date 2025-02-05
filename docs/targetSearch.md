# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product data.

## Usage
To use targetSearch, send a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target.
- `offset` (number, optional): The number of results to skip (for pagination).
- `category` (string, optional): Limit results to a specific product category.
- `fulfillment` (enum, optional): Filter by fulfillment method (e.g. "Pickup", "Shipping").
- `sort_by` (enum, optional): Sort results (e.g. "Relevance", "Price: Low to High").

## Return Value
Returns a JSON object containing search results with product details like name, brand, price, image URL, and more.

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

const data = await response.json();
console.log(data.parsing.search_results);

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

const data = await response.json();
console.log(data.parsing.search_results);
```

## Notes or Considerations
- Ensure you have a valid API token for authentication.
- The API has rate limits, so avoid making too many requests in a short time.
- Search results may vary based on location and inventory availability.
- Some product information may be incomplete or unavailable for certain items.