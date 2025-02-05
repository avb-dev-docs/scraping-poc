# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates searching for products on Amazon and extracting relevant data from the search results.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters. The object handles the URL construction, request formatting, and response parsing.

## Parameters
- `query` (string, required): The search term to look for on Amazon.

## Return Value
The amazonSearch object doesn't directly return a value. Instead, it provides a structure for making API requests that return search results data.

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
- Ensure you have the necessary authentication token to make requests.
- The search results will include various details about the products, such as ASIN, price, rating, and product name.
- The API response includes metadata such as the query time and status, in addition to the parsed search results.
- Be aware of Amazon's terms of service when using this API for scraping or data collection purposes.