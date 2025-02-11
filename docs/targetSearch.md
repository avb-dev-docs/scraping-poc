# targetSearch Documentation

## Brief Description

targetSearch is a JSON object that defines the configuration for performing product searches on Target's website and extracting structured data from the search results.

## Usage

This object is typically used as part of a larger system or API for scraping product data from Target. It defines the query parameters, URL structure, and parsing options for making Target product search requests and processing the results.

## Parameters

The `query_builder` property contains the following key parameters:

* `query` (string, required): The search term to look for on Target

* `offset` (number, optional): Pagination offset for search results

* `category` (string, optional): Target category ID to filter results

* `fulfillment` (enum, optional): Fulfillment method filter (e.g. "Pickup", "Shipping")

* `sort_by` (enum, optional): Sort order for results (e.g. "Relevance", "Price: Low to High")

## Return Value

This object does not return a value directly, but defines the structure for search requests and responses. The `example_response` shows the expected data format returned from a search, including product details like name, brand, price, ratings, etc.

## Examples

```javascript
// Example search request
{
  "endpoint": "https://api.webit.live/api/v1/realtime/ecommerce/target/search",
  "method": "POST", 
  "headers": {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  "body": {
    "query": "iron flask"
  }
}
```

## Notes or Considerations

* This object is meant to be used as part of a larger scraping/API system and not directly by end users

* It includes configurations for rendering the page and capturing network requests, which may require a headless browser

* The search functionality supports various filters and sorting options that can be customized

* Respect Target's terms of service and rate limits when using this for scraping
