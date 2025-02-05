# targetSearch Documentation

## Brief Description
targetSearch is an object that facilitates searching for products on Target's website and extracting relevant product information.

## Usage
To use targetSearch, make a POST request to the specified endpoint with the required parameters.

## Parameters
- `query` (string, required): The search term to look for on Target's website.
- `offset` (number, optional): The number of results to skip before starting to return data.
- `category` (string, optional): A specific category ID to filter results.
- `fulfillment` (string, optional): Filter by fulfillment method (e.g., "Pickup", "Shipping").
- `sort_by` (string, optional): Specify how to sort the results (e.g., "Relevance", "Price: Low to High").

## Return Value
targetSearch returns a JSON object containing search results from Target, including product details such as name, brand, price, and image URLs.

## Examples

### Basic Search
```json
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

### Search with Sorting and Fulfillment
```json
{
  "endpoint": "https://api.webit.live/api/v1/realtime/ecommerce/target/search",
  "method": "POST",
  "headers": {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  "body": {
    "query": "headphones",
    "sort_by": "Price: Low to High",
    "fulfillment": "Shipping"
  }
}
```

## Notes or Considerations
- Ensure you have a valid API token for authentication.
- The API may have rate limits or usage restrictions.
- Search results may vary based on product availability and Target's inventory.
- Some parameters like `category` require specific format (e.g., 5-character alphanumeric code).
- The `fulfillment` and `sort_by` parameters accept specific predefined values.
- Response parsing is handled automatically, providing structured product data.