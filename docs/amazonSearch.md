# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon and extracting relevant data from search results.

## Usage
To use amazonSearch, you need to make a POST request to the Amazon search endpoint with the required parameters. The object handles the query building and parsing of results.

## Parameters
- `query` (string, required): The search term to look up on Amazon.

## Return Value
amazonSearch returns a JSON object containing the search results, including details like product name, price, rating, and URL for each item found.

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
- An API token is required to use this endpoint. Make sure to replace `<TOKEN>` with your actual authorization token.
- The search is performed on Amazon.com by default, but other Amazon domains can be supported.
- The response includes various details about each product, such as ASIN, price, rating, and product name.
- Sponsored results may be included in the search results.
- The actual number of results returned may vary based on Amazon's search algorithm and availability.