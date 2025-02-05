# amazonSearch Documentation

## Brief Description
amazonSearch is an object that facilitates extracting data from Amazon search result pages for a given search keyword.

## Usage
To use amazonSearch, you need to make a POST request to the specified endpoint with the required parameters.

## Parameters
- `query` (string, required): The search keyword to be used for the Amazon search.

## Return Value
The function returns a JSON object containing the search results, including details such as product names, prices, ratings, and URLs.

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
- You need a valid authorization token to make requests.
- The search is performed on Amazon's US site by default, but other domains like 'co.uk' are also supported.
- The response includes various details about the search results, such as product ASINs, prices, ratings, and image URLs.
- Be mindful of Amazon's terms of service when using this API for scraping data.