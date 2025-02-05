# amazon_product Documentation

## Brief Description

`amazon_product` is an object that facilitates extracting data from an Amazon product page for a given ASIN (Amazon's Product ID).

## Usage

To use `amazon_product`, you need to make a POST request to the specified endpoint with the required parameters. This object is designed to be used with an API, not as a standalone JavaScript object.

## Parameters

- `asin` (string, required): The Amazon Standard Identification Number (ASIN) of the product. Must be a 10-character alphanumeric string.

## Return Value

The `amazon_product` object doesn't return a value directly. Instead, it provides a structure for making an API request that returns product data in JSON format.

## Examples

### Example Request:

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

### Example Response:

```json
{
  "url": "https://www.amazon.com/dp/B0C4ZZBD71",
  "asin": "B0C4ZZBD71",
  "status": "success",
  "query_time": "2024-06-20T15:34:55.225Z",
  "status_code": 200,
  "parsing": {
    "product": [
      {
        "asin": "B0C4ZZBD71",
        "parent_asin": "B0CNHQ1QM5",
        "availability": "In Stock",
        "entity_type": "Product",
        "price": "$34.99",
        "old_price": "$34.99",
        "image_url": "https://images-na.ssl-images-amazon.com/images/G/01/x-locale/common/grey-pixel.gif",
        "rating": "4.6 out of 5 stars",
        "reviewsCount": "1,636 ratings",
        "product_name": "IRON FLASK Co-Pilot Insulated Mug w/Straw & Flip Cap Lids - Cup Holder Bottle for Hot, Cold Drink - Leak-Proof - Water, Coffee Portable Travel Mug - Aurora, 40 Oz",
        // ... (additional product details)
      }
    ]
  }
}
```

## Notes or Considerations

1. You must have a valid API token to make requests using this object.
2. The API response includes detailed product information such as price, ratings, reviews, features, and variations.
3. The object supports multiple domains (e.g., "com", "co.uk"), defaulting to the US domain.
4. Ensure that you handle potential errors or unsuccessful responses in your implementation.
5. The data returned may vary depending on the product and its availability on Amazon.