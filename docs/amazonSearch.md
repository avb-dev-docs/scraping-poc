# amazonSearch Documentation

## Brief Description

amazonSearch is a JSON object that defines the structure and parameters for making Amazon product search queries.

## Usage

To use amazonSearch, you need to send a POST request to the specified endpoint with the required parameters. The object provides the URL structure, query parameters, and parsing options for Amazon product searches.

## Parameters

* `query` (string, required): The search term to look up on Amazon.

## Return Value

The amazonSearch object doesn't return a value directly. Instead, it defines the structure for an API request that will return search results from Amazon.

## Examples

```javascript
// Example POST request using the amazonSearch structure
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

* You need a valid authorization token to make requests.

* The search is performed on Amazon's US site by default, but other domains like UK are supported.

* The response includes detailed product information such as ASIN, price, rating, and product name.

* Be aware of Amazon's terms of service and usage limits when using this API.
