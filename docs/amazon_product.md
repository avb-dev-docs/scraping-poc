# amazon_product Documentation

## Brief Description
The `amazon_product` object is a JSON configuration for extracting data from an Amazon product page given an ASIN (Amazon Standard Identification Number).

## Usage
This object is typically used as part of a larger API or system for scraping Amazon product data. It defines the structure and parameters needed to make a request to retrieve product information.

## Parameters
- `asin` (string, required): The Amazon Standard Identification Number of the product. Must be a 10-character alphanumeric string.

## Return Value
When used in an API request, this configuration returns a JSON object containing detailed product information from the Amazon page.

## Examples

```json
{
  "endpoint": "https://api.webit.live/api/v1/realtime/ecommerce/amazon/product",
  "method": "POST",
  "headers": {
    "Authorization": "Basic <TOKEN>",
    "Content-Type": "application/json"
  },
  "body": {
    "asin": "B0C4ZZBD71"
  }
}
```

## Notes or Considerations
- This object is designed to work with a specific API endpoint (https://api.webit.live/api/v1/realtime/ecommerce/amazon/product).
- The API requires authentication via a token in the Authorization header.
- The object includes configurations for different Amazon domains (.com, .co.uk), defaulting to the US store.
- The returned data includes comprehensive product details such as price, rating, reviews, features, and variations.
- Ensure you comply with Amazon's terms of service and robots.txt when using this for web scraping.