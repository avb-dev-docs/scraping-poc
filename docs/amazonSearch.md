# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon and extracting relevant data from the search results.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters. The object handles the query building and parsing of the search results.

## Parameters
- `query` (string, required): The search term to look for on Amazon.

## Return Value
amazonSearch returns a JSON object containing the search results, including details such as product names, prices, ratings, and URLs.

## Examples

```javascript
// Example POST request
fetch('https://api.webit.live/api/v1/realtime/ecommerce/amazon/search', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    query: 'ironflask'
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

## Notes or Considerations
- You need a valid API token to access this endpoint.
- The search is performed on Amazon's US site by default, but other domains like UK are supported.
- The results include sponsored products, which are marked accordingly.
- The number of results and the exact fields returned may vary depending on the search query and Amazon's current layout.
- Be mindful of Amazon's terms of service when using this API for scraping data.