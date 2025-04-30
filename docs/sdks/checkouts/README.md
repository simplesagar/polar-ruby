# Checkouts
(*checkouts*)

## Overview

### Available Operations

* [list](#list) - List Checkout Sessions
* [create](#create) - Create Checkout Session
* [get](#get) - Get Checkout Session
* [client_get](#client_get) - Get Checkout Session from Client

## list

List checkout sessions.

**Scopes**: `checkouts:read` `checkouts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::CheckoutsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.checkouts.list(req)

if ! res.list_resource_checkout.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `request`                                                                                   | [Models::Operations::CheckoutsListRequest](../../models/operations/checkoutslistrequest.md) | :heavy_check_mark:                                                                          | The request object to use for the request.                                                  |

### Response

**[T.nilable(Models::Operations::CheckoutsListResponse)](../../models/operations/checkoutslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a checkout session.

**Scopes**: `checkouts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::CheckoutCreate.new(
  customer_billing_address: Models::Shared::Address.new(
    country: "SE",
  ),
  products: [
    "<value>",
  ],
)

res = s.checkouts.create(req)

if ! res.checkout.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [Models::Shared::CheckoutCreate](../../models/shared/checkoutcreate.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |

### Response

**[T.nilable(Models::Operations::CheckoutsCreateResponse)](../../models/operations/checkoutscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a checkout session by ID.

**Scopes**: `checkouts:read` `checkouts:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.checkouts.get(id="<value>")

if ! res.checkout.nil?
  # handle response
end

```

### Parameters

| Parameter                | Type                     | Required                 | Description              |
| ------------------------ | ------------------------ | ------------------------ | ------------------------ |
| `id`                     | *::String*               | :heavy_check_mark:       | The checkout session ID. |

### Response

**[T.nilable(Models::Operations::CheckoutsGetResponse)](../../models/operations/checkoutsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## client_get

Get a checkout session by client secret.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.checkouts.client_get(client_secret="<value>")

if ! res.checkout_public.nil?
  # handle response
end

```

### Parameters

| Parameter                           | Type                                | Required                            | Description                         |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `client_secret`                     | *::String*                          | :heavy_check_mark:                  | The checkout session client secret. |

### Response

**[T.nilable(Models::Operations::CheckoutsClientGetResponse)](../../models/operations/checkoutsclientgetresponse.md)**

### Errors

| Error Type                           | Status Code                          | Content Type                         |
| ------------------------------------ | ------------------------------------ | ------------------------------------ |
| Models::Errors::ResourceNotFound     | 404                                  | application/json                     |
| Models::Errors::ExpiredCheckoutError | 410                                  | application/json                     |
| Models::Errors::HTTPValidationError  | 422                                  | application/json                     |
| Errors::APIError                     | 4XX, 5XX                             | \*/\*                                |