# Discounts
(*discounts*)

## Overview

### Available Operations

* [list](#list) - List Discounts
* [create](#create) - Create Discount
* [get](#get) - Get Discount
* [update](#update) - Update Discount
* [delete](#delete) - Delete Discount

## list

List discounts.

**Scopes**: `discounts:read` `discounts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::DiscountsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.discounts.list(req)

if ! res.list_resource_discount.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `request`                                                                                   | [Models::Operations::DiscountsListRequest](../../models/operations/discountslistrequest.md) | :heavy_check_mark:                                                                          | The request object to use for the request.                                                  |

### Response

**[T.nilable(Models::Operations::DiscountsListResponse)](../../models/operations/discountslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a discount.

**Scopes**: `discounts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::DiscountFixedRepeatDurationCreate.new(
  duration: Models::Shared::DiscountDuration::FOREVER,
  duration_in_months: 417_458,
  type: Models::Shared::DiscountType::FIXED,
  amount: 69_025,
  name: "<value>",
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
)

res = s.discounts.create(req)

if ! res.discount.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                                      | Type                                                                                                                                                                                                                                                                           | Required                                                                                                                                                                                                                                                                       | Description                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                                                                                                                      | [T.any(Models::Shared::DiscountFixedOnceForeverDurationCreate, Models::Shared::DiscountFixedRepeatDurationCreate, Models::Shared::DiscountPercentageOnceForeverDurationCreate, Models::Shared::DiscountPercentageRepeatDurationCreate)](../../models/shared/discountcreate.md) | :heavy_check_mark:                                                                                                                                                                                                                                                             | The request object to use for the request.                                                                                                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::DiscountsCreateResponse)](../../models/operations/discountscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a discount by ID.

**Scopes**: `discounts:read` `discounts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.discounts.get(id="<value>")

if ! res.discount.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The discount ID.   |

### Response

**[T.nilable(Models::Operations::DiscountsGetResponse)](../../models/operations/discountsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a discount.

**Scopes**: `discounts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.discounts.update(id="<value>", discount_update=Models::Shared::DiscountUpdate.new())

if ! res.discount.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `id`                                                                    | *::String*                                                              | :heavy_check_mark:                                                      | The discount ID.                                                        |
| `discount_update`                                                       | [Models::Shared::DiscountUpdate](../../models/shared/discountupdate.md) | :heavy_check_mark:                                                      | N/A                                                                     |

### Response

**[T.nilable(Models::Operations::DiscountsUpdateResponse)](../../models/operations/discountsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a discount.

**Scopes**: `discounts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.discounts.delete(id="<value>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The discount ID.   |

### Response

**[T.nilable(Models::Operations::DiscountsDeleteResponse)](../../models/operations/discountsdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |