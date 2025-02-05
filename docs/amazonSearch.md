# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon and extracting relevant data from the search results.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters. The object handles the construction of the Amazon search URL and parsing of the results.

## Parameters
- `query` (string, required): The search term to look for on Amazon.

## Return Value
amazonSearch returns a JSON object containing the search results, including details like product name, price, rating, and image URL for each item found.

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
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

## Notes or Considerations
- You need a valid authorization token to use this API.
- The search is performed on Amazon.com by default, but can be configured for other Amazon domains.
- The results include sponsored products, which are marked accordingly.
- The number of results and the exact fields returned may vary depending on the search term and Amazon's current layout.
- Be mindful of Amazon's terms of service when using this API for frequent or automated searches.