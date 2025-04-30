# CustomerPortalOrders
(*customer_portal_orders*)

## Overview

### Available Operations

* [list](#list) - List Orders
* [get](#get) - Get Order
* [invoice](#invoice) - Get Order Invoice

## list

List orders of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Operations::CustomerPortalOrdersListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.customer_portal_orders.list(security: Models::Operations::CustomerPortalOrdersListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), req, Models::Operations::CustomerPortalOrdersListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.list_resource_customer_order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                           | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                           | [Models::Operations::CustomerPortalOrdersListRequest](../../models/operations/customerportalorderslistrequest.md)   | :heavy_check_mark:                                                                                                  | The request object to use for the request.                                                                          |
| `security`                                                                                                          | [Models::Operations::CustomerPortalOrdersListSecurity](../../models/operations/customerportalorderslistsecurity.md) | :heavy_check_mark:                                                                                                  | The security requirements to use for the request.                                                                   |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersListResponse)](../../models/operations/customerportalorderslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an order by ID for the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_orders.get(security: Models::Operations::CustomerPortalOrdersGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalOrdersGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.customer_order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                         | Type                                                                                                              | Required                                                                                                          | Description                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                        | [Models::Operations::CustomerPortalOrdersGetSecurity](../../models/operations/customerportalordersgetsecurity.md) | :heavy_check_mark:                                                                                                | The security requirements to use for the request.                                                                 |
| `id`                                                                                                              | *::String*                                                                                                        | :heavy_check_mark:                                                                                                | The order ID.                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersGetResponse)](../../models/operations/customerportalordersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## invoice

Get an order's invoice data.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_orders.invoice(security: Models::Operations::CustomerPortalOrdersInvoiceSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalOrdersInvoiceSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.customer_order_invoice.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                 | Type                                                                                                                      | Required                                                                                                                  | Description                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                | [Models::Operations::CustomerPortalOrdersInvoiceSecurity](../../models/operations/customerportalordersinvoicesecurity.md) | :heavy_check_mark:                                                                                                        | The security requirements to use for the request.                                                                         |
| `id`                                                                                                                      | *::String*                                                                                                                | :heavy_check_mark:                                                                                                        | The order ID.                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersInvoiceResponse)](../../models/operations/customerportalordersinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |