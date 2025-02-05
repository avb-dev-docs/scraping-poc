# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon using a given keyword.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters.

## Parameters
- `query` (string, required): The search keyword or phrase to look up on Amazon.

## Return Value
The function returns a JSON object containing search results from Amazon, including product details like ASIN, price, rating, and product name.

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
- You need a valid authorization token to make requests to the API.
- The search is performed on Amazon's US site by default, but other domains like Amazon UK are also supported.
- The API may have rate limits or usage restrictions, so check the service documentation for details.
- The returned data includes various details about the products, which can be used for price comparison, product analysis, or other e-commerce applications.