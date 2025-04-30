# Customers
(*customers*)

## Overview

### Available Operations

* [list](#list) - List Customers
* [create](#create) - Create Customer
* [get](#get) - Get Customer
* [update](#update) - Update Customer
* [delete](#delete) - Delete Customer
* [get_external](#get_external) - Get Customer by External ID
* [update_external](#update_external) - Update Customer by External ID
* [delete_external](#delete_external) - Delete Customer by External ID
* [get_state](#get_state) - Get Customer State
* [get_state_external](#get_state_external) - Get Customer State by External ID

## list

List customers.

**Scopes**: `customers:read` `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::CustomersListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.customers.list(req)

if ! res.list_resource_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `request`                                                                                   | [Models::Operations::CustomersListRequest](../../models/operations/customerslistrequest.md) | :heavy_check_mark:                                                                          | The request object to use for the request.                                                  |

### Response

**[T.nilable(Models::Operations::CustomersListResponse)](../../models/operations/customerslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a customer.

**Scopes**: `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::CustomerCreate.new(
  external_id: "usr_1337",
  email: "customer@example.com",
  name: "John Doe",
  billing_address: Models::Shared::Address.new(
    country: "SE",
  ),
  tax_id: [
    "FR61954506077",
    "eu_vat",
  ],
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
)

res = s.customers.create(req)

if ! res.customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [Models::Shared::CustomerCreate](../../models/shared/customercreate.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |

### Response

**[T.nilable(Models::Operations::CustomersCreateResponse)](../../models/operations/customerscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a customer by ID.

**Scopes**: `customers:read` `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.get(id="<value>")

if ! res.customer.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The customer ID.   |

### Response

**[T.nilable(Models::Operations::CustomersGetResponse)](../../models/operations/customersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a customer.

**Scopes**: `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.update(id="<value>", customer_update=Models::Shared::CustomerUpdate.new(
  email: "customer@example.com",
  name: "John Doe",
  billing_address: Models::Shared::Address.new(
    country: "FR",
  ),
  tax_id: [
    "FR61954506077",
    "eu_vat",
  ],
  external_id: "usr_1337",
))

if ! res.customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `id`                                                                    | *::String*                                                              | :heavy_check_mark:                                                      | The customer ID.                                                        |
| `customer_update`                                                       | [Models::Shared::CustomerUpdate](../../models/shared/customerupdate.md) | :heavy_check_mark:                                                      | N/A                                                                     |

### Response

**[T.nilable(Models::Operations::CustomersUpdateResponse)](../../models/operations/customersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a customer.

This action cannot be undone and will immediately:
- Cancel any active subscriptions for the customer
- Revoke all their benefits
- Clear any `external_id`

Use it only in the context of deleting a user within your
own service. Otherwise, use more granular API endpoints to cancel
a specific subscription or revoke certain benefits.

Note: The customers information will nonetheless be retained for historic
orders and subscriptions.

**Scopes**: `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.delete(id="<value>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The customer ID.   |

### Response

**[T.nilable(Models::Operations::CustomersDeleteResponse)](../../models/operations/customersdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_external

Get a customer by external ID.

**Scopes**: `customers:read` `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.get_external(external_id="<id>")

if ! res.customer.nil?
  # handle response
end

```

### Parameters

| Parameter                 | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `external_id`             | *::String*                | :heavy_check_mark:        | The customer external ID. |

### Response

**[T.nilable(Models::Operations::CustomersGetExternalResponse)](../../models/operations/customersgetexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_external

Update a customer by external ID.

**Scopes**: `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.update_external(external_id="<id>", customer_update_external_id=Models::Shared::CustomerUpdateExternalID.new(
  email: "customer@example.com",
  name: "John Doe",
  billing_address: Models::Shared::Address.new(
    country: "US",
  ),
  tax_id: [
    "FR61954506077",
    "eu_vat",
  ],
))

if ! res.customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `external_id`                                                                               | *::String*                                                                                  | :heavy_check_mark:                                                                          | The customer external ID.                                                                   |
| `customer_update_external_id`                                                               | [Models::Shared::CustomerUpdateExternalID](../../models/shared/customerupdateexternalid.md) | :heavy_check_mark:                                                                          | N/A                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomersUpdateExternalResponse)](../../models/operations/customersupdateexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_external

Delete a customer by external ID.

Immediately cancels any active subscriptions and revokes any active benefits.

**Scopes**: `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.delete_external(external_id="<id>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                 | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `external_id`             | *::String*                | :heavy_check_mark:        | The customer external ID. |

### Response

**[T.nilable(Models::Operations::CustomersDeleteExternalResponse)](../../models/operations/customersdeleteexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_state

Get a customer state by ID.

The customer state includes information about
the customer's active subscriptions and benefits.

It's the ideal endpoint to use when you need to get a full overview
of a customer's status.

**Scopes**: `customers:read` `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.get_state(id="<value>")

if ! res.customer_state.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The customer ID.   |

### Response

**[T.nilable(Models::Operations::CustomersGetStateResponse)](../../models/operations/customersgetstateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_state_external

Get a customer state by external ID.

The customer state includes information about
the customer's active subscriptions and benefits.

It's the ideal endpoint to use when you need to get a full overview
of a customer's status.

**Scopes**: `customers:read` `customers:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customers.get_state_external(external_id="<id>")

if ! res.customer_state.nil?
  # handle response
end

```

### Parameters

| Parameter                 | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `external_id`             | *::String*                | :heavy_check_mark:        | The customer external ID. |

### Response

**[T.nilable(Models::Operations::CustomersGetStateExternalResponse)](../../models/operations/customersgetstateexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |