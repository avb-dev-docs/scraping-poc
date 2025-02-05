# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product information.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip before starting to return products.
- `category` (string, optional): A specific category ID to filter results.
- `fulfillment` (string, optional): Filter by fulfillment method (e.g., "Pickup", "Shipping").
- `sort_by` (string, optional): Specify how to sort the results (e.g., "Relevance", "Price: Low to High").

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, rating, and image URLs.

## Examples

### Basic Search
```javascript
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
```

### Search with Sorting and Fulfillment Options
```javascript
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
- Some parameters like `category` require specific format (e.g., 5-character alphanumeric code for category).
- The search results may include sponsored products, which are marked in the response.
- The API simulates user browsing behavior, including waiting for page elements and scrolling, which may affect response times.