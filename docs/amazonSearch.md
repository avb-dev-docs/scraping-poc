# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching Amazon's product catalog by constructing and executing search queries.

## Usage
To use amazonSearch, you need to make a POST request to the Amazon search endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term or keyword to look for on Amazon.

## Return Value
amazonSearch returns a JSON object containing the search results, including product details like ASIN, price, rating, name, and image URL for multiple products matching the search query.

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
- You need a valid authorization token to access the API.
- The search is performed on Amazon's US site by default, but can be configured for other country domains.
- The response includes various details about the products, which can be used for price comparison, product analysis, or displaying search results.
- Be aware of Amazon's terms of service and usage limits when using this API for frequent or high-volume searches.