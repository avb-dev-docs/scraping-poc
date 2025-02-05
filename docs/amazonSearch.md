# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon using a specified query.

## Usage
To use amazonSearch, you need to make a POST request to the Amazon search endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Amazon.

## Return Value
amazonSearch returns a JSON object containing search results from Amazon, including product details like ASIN, price, rating, and product name.

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
- The search results may include sponsored products.
- The number of results and the exact fields returned may vary depending on Amazon's response.
- Be mindful of rate limits and usage restrictions when making requests to the API.