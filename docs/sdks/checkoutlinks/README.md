# CheckoutLinks
(*checkout_links*)

## Overview

### Available Operations

* [list](#list) - List Checkout Links
* [create](#create) - Create Checkout Link
* [get](#get) - Get Checkout Link
* [update](#update) - Update Checkout Link
* [delete](#delete) - Delete Checkout Link

## list

List checkout links.

**Scopes**: `checkout_links:read` `checkout_links:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::CheckoutLinksListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.checkout_links.list(req)

if ! res.list_resource_checkout_link.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `request`                                                                                           | [Models::Operations::CheckoutLinksListRequest](../../models/operations/checkoutlinkslistrequest.md) | :heavy_check_mark:                                                                                  | The request object to use for the request.                                                          |

### Response

**[T.nilable(Models::Operations::CheckoutLinksListResponse)](../../models/operations/checkoutlinkslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a checkout link.

**Scopes**: `checkout_links:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::CheckoutLinkCreateProduct.new(
  payment_processor: "<value>",
  product_id: "<value>",
)

res = s.checkout_links.create(req)

if ! res.checkout_link.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                        | Type                                                                                                                                                                                                             | Required                                                                                                                                                                                                         | Description                                                                                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                                        | [T.any(Models::Shared::CheckoutLinkCreateProductPrice, Models::Shared::CheckoutLinkCreateProduct, Models::Shared::CheckoutLinkCreateProducts)](../../models/operations/checkoutlinkscreatecheckoutlinkcreate.md) | :heavy_check_mark:                                                                                                                                                                                               | The request object to use for the request.                                                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CheckoutLinksCreateResponse)](../../models/operations/checkoutlinkscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a checkout link by ID.

**Scopes**: `checkout_links:read` `checkout_links:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.checkout_links.get(id="<value>")

if ! res.checkout_link.nil?
  # handle response
end

```

### Parameters

| Parameter             | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `id`                  | *::String*            | :heavy_check_mark:    | The checkout link ID. |

### Response

**[T.nilable(Models::Operations::CheckoutLinksGetResponse)](../../models/operations/checkoutlinksgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a checkout link.

**Scopes**: `checkout_links:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.checkout_links.update(id="<value>", checkout_link_update=Models::Shared::CheckoutLinkUpdate.new())

if ! res.checkout_link.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `id`                                                                            | *::String*                                                                      | :heavy_check_mark:                                                              | The checkout link ID.                                                           |
| `checkout_link_update`                                                          | [Models::Shared::CheckoutLinkUpdate](../../models/shared/checkoutlinkupdate.md) | :heavy_check_mark:                                                              | N/A                                                                             |

### Response

**[T.nilable(Models::Operations::CheckoutLinksUpdateResponse)](../../models/operations/checkoutlinksupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a checkout link.

**Scopes**: `checkout_links:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.checkout_links.delete(id="<value>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter             | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `id`                  | *::String*            | :heavy_check_mark:    | The checkout link ID. |

### Response

**[T.nilable(Models::Operations::CheckoutLinksDeleteResponse)](../../models/operations/checkoutlinksdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |