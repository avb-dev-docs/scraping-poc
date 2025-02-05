# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting structured data from the search results.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters. The object handles the query building, rendering, and parsing of the search results.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip, used for pagination.
- `category` (string, optional): A category ID to filter results.
- `fulfillment` (string, optional): Filter by fulfillment method (e.g., "Pickup", "Shipping").
- `sort_by` (string, optional): Sort results by criteria like "Relevance", "Price: Low to High", etc.

## Return Value
The targetSearch object doesn't return a value directly, but the API response contains structured data about the search results, including product information, prices, ratings, and more.

## Examples

1. Basic search for "iron flask":

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

2. Search with additional parameters:

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
- Ensure you have the necessary API token for authentication.
- The API has a rendering process that may take some time, so expect a slight delay in responses.
- Be mindful of Target's terms of service and any rate limiting when using this API.
- The search results may include sponsored products, which are marked in the response.
- Some product information may be incomplete or vary based on the search results.