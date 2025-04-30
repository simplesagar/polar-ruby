# Refunds
(*refunds*)

## Overview

### Available Operations

* [list](#list) - List Refunds
* [create](#create) - Create Refund

## list

List products.

**Scopes**: `refunds:read` `refunds:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::RefundsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.refunds.list(req)

if ! res.list_resource_refund.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `request`                                                                               | [Models::Operations::RefundsListRequest](../../models/operations/refundslistrequest.md) | :heavy_check_mark:                                                                      | The request object to use for the request.                                              |

### Response

**[T.nilable(Models::Operations::RefundsListResponse)](../../models/operations/refundslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a refund.

**Scopes**: `refunds:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::RefundCreate.new(
  order_id: "<value>",
  reason: Models::Shared::RefundReason::CUSTOMER_REQUEST,
  amount: 638_424,
)

res = s.refunds.create(req)

if ! res.refund.nil?
  # handle response
end

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [Models::Shared::RefundCreate](../../models/shared/refundcreate.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[T.nilable(Models::Operations::RefundsCreateResponse)](../../models/operations/refundscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::RefundAmountTooHigh | 400                                 | application/json                    |
| Models::Errors::RefundedAlready     | 403                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |