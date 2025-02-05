# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product information.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for products on Target.
- `offset` (number, optional): The number of results to skip before starting to return products.
- `category` (string, optional): A category ID to filter results.
- `fulfillment` (string, optional): Filter by fulfillment method (e.g. "Pickup", "Shipping").
- `sort_by` (string, optional): Sort results by different criteria (e.g. "Relevance", "Price: Low to High").

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, image URL, and more.

## Examples

```javascript
// Example 1: Basic search
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

// Example 2: Search with additional parameters
const response = await fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
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
- The API has rate limiting, so be mindful of the number of requests you make.
- Search results may vary based on inventory and regional availability.
- Some optional parameters like `category` require specific format (e.g., 5-digit alphanumeric code for category).
- The API simulates user behavior by scrolling through search results, which may affect response time.