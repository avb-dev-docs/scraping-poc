# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant data from the search results.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip before starting to return data.
- `category` (string, optional): Limits the search to a specific product category.
- `fulfillment` (string, optional): Filters results by fulfillment method (e.g., "Pickup", "Shipping").
- `sort_by` (string, optional): Determines the order of search results (e.g., "Relevance", "Price: Low to High").

## Return Value
The targetSearch object doesn't directly return a value, but the API response contains search results including product details such as name, brand, price, rating, and image URL.

## Examples

1. Basic search:
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
    fulfillment: 'Shipping',
    sort_by: 'Price: Low to High'
  })
});
const data = await response.json();
```

## Notes or Considerations
- Ensure you have the necessary API token for authentication.
- The API has a render option that simulates browser behavior, which may impact response times.
- Be aware of any rate limiting or usage restrictions imposed by the API provider.
- The search results may include sponsored products, which are marked in the response.
- Some optional parameters like `category` require specific formatting (e.g., a 5-character alphanumeric string for category).