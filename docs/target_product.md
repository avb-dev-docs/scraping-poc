# target\_product Documentation

## Brief Description

`target_product` is a JSON object that defines an API endpoint for extracting product data from a Target product page using a given Target product ID (TCIN).

## Usage

This object is used to configure API requests to retrieve detailed information about a specific product on Target's website. It specifies the URL structure, required parameters, and parsing options for the API call.

## Parameters

* `tcin` (string, required): The Target product ID, must be an 8-digit number.

## Return Value

The API call configured by this object returns a JSON response containing detailed product information from the Target website.

## Examples

```javascript
// Example API request
fetch('https://api.webit.live/api/v1/realtime/ecommerce/target/product', {
  method: 'POST',
  headers: {
    'Authorization': 'Basic <YOUR_TOKEN>',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    tcin: '87973629'
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

## Notes or Considerations

* This object is designed for use with a specific API (webit.live) and may not work with other services.

* The API requires authentication, so make sure to include a valid authorization token in your requests.

* The response includes various details about the product, such as name, brand, price, description, images, and customer reviews.

* The API uses browser rendering to capture dynamic content, which may affect response times.

* Be mindful of Target's terms of service and any rate limiting when using this API in your applications.
