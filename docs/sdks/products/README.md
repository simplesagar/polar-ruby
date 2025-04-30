# Products
(*products*)

## Overview

### Available Operations

* [list](#list) - List Products
* [create](#create) - Create Product
* [get](#get) - Get Product
* [update](#update) - Update Product
* [update_benefits](#update_benefits) - Update Product Benefits

## list

List products.

**Scopes**: `products:read` `products:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::ProductsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.products.list(req)

if ! res.list_resource_product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `request`                                                                                 | [Models::Operations::ProductsListRequest](../../models/operations/productslistrequest.md) | :heavy_check_mark:                                                                        | The request object to use for the request.                                                |

### Response

**[T.nilable(Models::Operations::ProductsListResponse)](../../models/operations/productslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a product.

**Scopes**: `products:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::ProductCreate.new(
  name: "<value>",
  recurring_interval: Models::Shared::SubscriptionRecurringInterval::MONTH,
  prices: [
    Models::Shared::ProductPriceFreeCreate.new(
      amount_type: "<value>",
    ),
  ],
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
)

res = s.products.create(req)

if ! res.product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `request`                                                             | [Models::Shared::ProductCreate](../../models/shared/productcreate.md) | :heavy_check_mark:                                                    | The request object to use for the request.                            |

### Response

**[T.nilable(Models::Operations::ProductsCreateResponse)](../../models/operations/productscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a product by ID.

**Scopes**: `products:read` `products:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.products.get(id="<value>")

if ! res.product.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ProductsGetResponse)](../../models/operations/productsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a product.

**Scopes**: `products:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.products.update(id="<value>", product_update=Models::Shared::ProductUpdate.new())

if ! res.product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `id`                                                                  | *::String*                                                            | :heavy_check_mark:                                                    | N/A                                                                   |
| `product_update`                                                      | [Models::Shared::ProductUpdate](../../models/shared/productupdate.md) | :heavy_check_mark:                                                    | N/A                                                                   |

### Response

**[T.nilable(Models::Operations::ProductsUpdateResponse)](../../models/operations/productsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_benefits

Update benefits granted by a product.

**Scopes**: `products:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.products.update_benefits(id="<value>", product_benefits_update=Models::Shared::ProductBenefitsUpdate.new(
  benefits: [
    "<value>",
  ],
))

if ! res.product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `id`                                                                                  | *::String*                                                                            | :heavy_check_mark:                                                                    | N/A                                                                                   |
| `product_benefits_update`                                                             | [Models::Shared::ProductBenefitsUpdate](../../models/shared/productbenefitsupdate.md) | :heavy_check_mark:                                                                    | N/A                                                                                   |

### Response

**[T.nilable(Models::Operations::ProductsUpdateBenefitsResponse)](../../models/operations/productsupdatebenefitsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |