# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product information.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip before starting to return products.
- `category` (string, optional): A specific category ID to filter results.
- `fulfillment` (string, optional): Filter by fulfillment method (e.g., "Pickup", "Shop in Store", "Same Day Delivery", "Shipping").
- `sort_by` (string, optional): Sorting criteria for results (e.g., "Relevance", "Price: Low to High", "Best Seller").

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, rating, and image URLs.

## Examples

### Basic search
```javascript
fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'iron flask'
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

### Search with additional parameters
```javascript
fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'headphones',
    fulfillment: 'Pickup',
    sort_by: 'Price: Low to High'
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

## Notes or Considerations
- Ensure you have a valid API token for authentication.
- The API has rate limits and usage restrictions, so check the service documentation for details.
- Search results may vary based on location and product availability.
- Some parameters like `category` require specific format (e.g., 5-character string), so refer to Target's documentation for valid values.
- The API uses a render flow to capture dynamic content, which may affect response times.