# CustomerPortalCustomerMeters
(*customer_portal_customer_meters*)

## Overview

### Available Operations

* [list](#list) - List Meters
* [get](#get) - Get Customer Meter

## list

List meters of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Operations::CustomerPortalCustomerMetersListRequest.new()

res = s.customer_portal_customer_meters.list(security: Models::Operations::CustomerPortalCustomerMetersListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), req, Models::Operations::CustomerPortalCustomerMetersListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.list_resource_customer_customer_meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                           | Type                                                                                                                                | Required                                                                                                                            | Description                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                           | [Models::Operations::CustomerPortalCustomerMetersListRequest](../../models/operations/customerportalcustomermeterslistrequest.md)   | :heavy_check_mark:                                                                                                                  | The request object to use for the request.                                                                                          |
| `security`                                                                                                                          | [Models::Operations::CustomerPortalCustomerMetersListSecurity](../../models/operations/customerportalcustomermeterslistsecurity.md) | :heavy_check_mark:                                                                                                                  | The security requirements to use for the request.                                                                                   |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerMetersListResponse)](../../models/operations/customerportalcustomermeterslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a meter by ID for the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_customer_meters.get(security: Models::Operations::CustomerPortalCustomerMetersGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalCustomerMetersGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.customer_customer_meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                         | Type                                                                                                                              | Required                                                                                                                          | Description                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                        | [Models::Operations::CustomerPortalCustomerMetersGetSecurity](../../models/operations/customerportalcustomermetersgetsecurity.md) | :heavy_check_mark:                                                                                                                | The security requirements to use for the request.                                                                                 |
| `id`                                                                                                                              | *::String*                                                                                                                        | :heavy_check_mark:                                                                                                                | The customer meter ID.                                                                                                            |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerMetersGetResponse)](../../models/operations/customerportalcustomermetersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |