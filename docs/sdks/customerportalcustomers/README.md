# CustomerPortalCustomers
(*customer_portal_customers*)

## Overview

### Available Operations

* [get](#get) - Get Customer
* [update](#update) - Update Customer
* [get_payment_methods](#get_payment_methods) - Get Customer Payment Methods
* [add_payment_method](#add_payment_method) - Add Customer Payment Method
* [delete_payment_method](#delete_payment_method) - Delete Customer Payment Method

## get

Get authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_customers.get(security: Models::Operations::CustomerPortalCustomersGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalCustomersGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.customer_portal_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                               | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                              | [Models::Operations::CustomerPortalCustomersGetSecurity](../../models/operations/customerportalcustomersgetsecurity.md) | :heavy_check_mark:                                                                                                      | The security requirements to use for the request.                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersGetResponse)](../../models/operations/customerportalcustomersgetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update

Update authenticated customer.

**Scopes**: `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::CustomerPortalCustomerUpdate.new(
  billing_address: Models::Shared::Address.new(
    country: "FR",
  ),
)

res = s.customer_portal_customers.update(security: Models::Operations::CustomerPortalCustomersUpdateSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), req, Models::Operations::CustomerPortalCustomersUpdateSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.customer_portal_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                     | [Models::Shared::CustomerPortalCustomerUpdate](../../models/shared/customerportalcustomerupdate.md)                           | :heavy_check_mark:                                                                                                            | The request object to use for the request.                                                                                    |
| `security`                                                                                                                    | [Models::Operations::CustomerPortalCustomersUpdateSecurity](../../models/operations/customerportalcustomersupdatesecurity.md) | :heavy_check_mark:                                                                                                            | The security requirements to use for the request.                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersUpdateResponse)](../../models/operations/customerportalcustomersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_payment_methods

Get saved payment methods of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_customers.get_payment_methods(security: Models::Operations::CustomerPortalCustomersGetPaymentMethodsSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalCustomersGetPaymentMethodsSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), page=842_307, limit=819_707)

if ! res.list_resource_union_payment_method_card_payment_method_generic.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                           | Type                                                                                                                                                | Required                                                                                                                                            | Description                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                          | [Models::Operations::CustomerPortalCustomersGetPaymentMethodsSecurity](../../models/operations/customerportalcustomersgetpaymentmethodssecurity.md) | :heavy_check_mark:                                                                                                                                  | The security requirements to use for the request.                                                                                                   |
| `page`                                                                                                                                              | *T.nilable(::Integer)*                                                                                                                              | :heavy_minus_sign:                                                                                                                                  | Page number, defaults to 1.                                                                                                                         |
| `limit`                                                                                                                                             | *T.nilable(::Integer)*                                                                                                                              | :heavy_minus_sign:                                                                                                                                  | Size of a page, defaults to 10. Maximum is 100.                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersGetPaymentMethodsResponse)](../../models/operations/customerportalcustomersgetpaymentmethodsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## add_payment_method

Add a payment method to the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::CustomerPaymentMethodCreate.new(
  confirmation_token_id: "<id>",
  set_default: false,
  return_url: "https://probable-resource.biz",
)

res = s.customer_portal_customers.add_payment_method(security: Models::Operations::CustomerPortalCustomersAddPaymentMethodSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), req, Models::Operations::CustomerPortalCustomersAddPaymentMethodSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.response_customer_portal_customers_add_payment_method.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                         | Type                                                                                                                                              | Required                                                                                                                                          | Description                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                         | [Models::Shared::CustomerPaymentMethodCreate](../../models/shared/customerpaymentmethodcreate.md)                                                 | :heavy_check_mark:                                                                                                                                | The request object to use for the request.                                                                                                        |
| `security`                                                                                                                                        | [Models::Operations::CustomerPortalCustomersAddPaymentMethodSecurity](../../models/operations/customerportalcustomersaddpaymentmethodsecurity.md) | :heavy_check_mark:                                                                                                                                | The security requirements to use for the request.                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersAddPaymentMethodResponse)](../../models/operations/customerportalcustomersaddpaymentmethodresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_payment_method

Delete a payment method from the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_customers.delete_payment_method(security: Models::Operations::CustomerPortalCustomersDeletePaymentMethodSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalCustomersDeletePaymentMethodSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<id>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                               | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                              | [Models::Operations::CustomerPortalCustomersDeletePaymentMethodSecurity](../../models/operations/customerportalcustomersdeletepaymentmethodsecurity.md) | :heavy_check_mark:                                                                                                                                      | The security requirements to use for the request.                                                                                                       |
| `id`                                                                                                                                                    | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersDeletePaymentMethodResponse)](../../models/operations/customerportalcustomersdeletepaymentmethodresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |