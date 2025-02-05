# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon using a given keyword.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters.

## Parameters
- `query` (string, required): The search keyword or phrase to look for on Amazon.

## Return Value
The amazonSearch object returns a JSON response containing search results from Amazon, including product details like ASIN, price, rating, and product name.

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
- The search is performed on Amazon's US site by default, but can be configured for other country domains.
- The response includes various details about the search results, such as product names, prices, ratings, and image URLs.
- Be aware of Amazon's terms of service and rate limits when using this API for frequent searches.