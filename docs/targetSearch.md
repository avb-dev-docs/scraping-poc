# targetSearch Documentation

## Brief Description

targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product information.

## Usage

To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters

- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip before starting to return products.
- `category` (string, optional): A specific category ID to limit the search results.
- `fulfillment` (enum, optional): Filter results by fulfillment method. Options include "Pickup", "Shop in Store", "Same Day Delivery", and "Shipping".
- `sort_by` (enum, optional): Sort the results. Options include "Relevance", "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", and "Newest".

## Return Value

The API returns a JSON object containing search results, including product details such as name, brand, price, rating, and product identifiers.

## Examples

```javascript
// Basic search for "iron flask"
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

// Search for "headphones" with sorting and fulfillment options
fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/search', {
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
})
.then(response => response.json())
.then(data => console.log(data));
```

## Notes or Considerations

- Ensure you have a valid API token for authentication.
- The API uses web scraping techniques, so be mindful of Target's terms of service and rate limiting.
- The search results may not always be exhaustive or real-time due to the nature of web scraping.
- Some product information may be incomplete or missing depending on Target's website structure and data availability.
- Consider implementing error handling and retries in your code to deal with potential API failures or timeouts.