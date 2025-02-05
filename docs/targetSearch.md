# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates product searches on Target's website, allowing users to extract data from Target search result pages.

## Usage
To use targetSearch, you need to make a POST request to the Target search API endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip before starting to return data.
- `category` (string, optional): A 5-character alphanumeric code to filter results by category.
- `fulfillment` (enum, optional): Filter results by fulfillment method. Options: "Pickup", "Shop in Store", "Same Day Delivery", "Shipping".
- `sort_by` (enum, optional): Sort the results. Default is "Relevance". Other options include "Featured", "Price: Low to High", "Price: High to Low", "Average Ratings", "Best Seller", "Newest".

## Return Value
The API returns a JSON object containing search results, including product details such as name, brand, price, image URL, and more.

## Examples

### Basic Search
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

### Search with Sorting and Fulfillment Options
```javascript
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
- Ensure you have the correct authorization token before making requests.
- The API uses a custom parsing system (parsit-ai) to extract data from Target's website.
- Be mindful of Target's website terms of use when utilizing this API.
- The search results may be paginated. Use the `offset` parameter for pagination if needed.
- Some products may have sponsored listings, which will be indicated in the response.
- The API simulates user interaction and page rendering, which may affect response times.