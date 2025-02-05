# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon and extracting relevant data from the search results.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters. The object handles the construction of the search URL and the parsing of the response.

## Parameters
- `query` (string, required): The search term to look for on Amazon.

## Return Value
The amazonSearch object doesn't directly return a value, but it processes the API response. The response includes:
- URL of the search results page
- Query used
- Status of the request
- Query time
- Status code
- Parsed search results, including details like ASIN, price, rating, product name, etc.

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
- Ensure you have the necessary authorization token to make requests to the API.
- The search is performed on Amazon.com by default, but other domains like Amazon.co.uk are supported.
- The response includes detailed information about each product in the search results, which can be used for various e-commerce analytics or comparison purposes.
- Be mindful of Amazon's terms of service when using this API for frequent or large-scale data extraction.