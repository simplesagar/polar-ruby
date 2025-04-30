# CustomerPortalSubscriptions
(*customer_portal_subscriptions*)

## Overview

### Available Operations

* [list](#list) - List Subscriptions
* [get](#get) - Get Subscription
* [update](#update) - Update Subscription
* [cancel](#cancel) - Cancel Subscription

## list

List subscriptions of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Operations::CustomerPortalSubscriptionsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.customer_portal_subscriptions.list(security: Models::Operations::CustomerPortalSubscriptionsListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), req, Models::Operations::CustomerPortalSubscriptionsListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.list_resource_customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                         | Type                                                                                                                              | Required                                                                                                                          | Description                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                         | [Models::Operations::CustomerPortalSubscriptionsListRequest](../../models/operations/customerportalsubscriptionslistrequest.md)   | :heavy_check_mark:                                                                                                                | The request object to use for the request.                                                                                        |
| `security`                                                                                                                        | [Models::Operations::CustomerPortalSubscriptionsListSecurity](../../models/operations/customerportalsubscriptionslistsecurity.md) | :heavy_check_mark:                                                                                                                | The security requirements to use for the request.                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsListResponse)](../../models/operations/customerportalsubscriptionslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a subscription for the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_subscriptions.get(security: Models::Operations::CustomerPortalSubscriptionsGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalSubscriptionsGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                       | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                      | [Models::Operations::CustomerPortalSubscriptionsGetSecurity](../../models/operations/customerportalsubscriptionsgetsecurity.md) | :heavy_check_mark:                                                                                                              | The security requirements to use for the request.                                                                               |
| `id`                                                                                                                            | *::String*                                                                                                                      | :heavy_check_mark:                                                                                                              | The subscription ID.                                                                                                            |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsGetResponse)](../../models/operations/customerportalsubscriptionsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a subscription of the authenticated customer.

**Scopes**: `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_subscriptions.update(security: Models::Operations::CustomerPortalSubscriptionsUpdateSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalSubscriptionsUpdateSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>", customer_subscription_update=Models::Shared::CustomerSubscriptionCancel.new())

if ! res.customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                 | Type                                                                                                                                                      | Required                                                                                                                                                  | Description                                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                | [Models::Operations::CustomerPortalSubscriptionsUpdateSecurity](../../models/operations/customerportalsubscriptionsupdatesecurity.md)                     | :heavy_check_mark:                                                                                                                                        | The security requirements to use for the request.                                                                                                         |
| `id`                                                                                                                                                      | *::String*                                                                                                                                                | :heavy_check_mark:                                                                                                                                        | The subscription ID.                                                                                                                                      |
| `customer_subscription_update`                                                                                                                            | [T.any(Models::Shared::CustomerSubscriptionUpdateProduct, Models::Shared::CustomerSubscriptionCancel)](../../models/shared/customersubscriptionupdate.md) | :heavy_check_mark:                                                                                                                                        | N/A                                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsUpdateResponse)](../../models/operations/customerportalsubscriptionsupdateresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |

## cancel

Cancel a subscription of the authenticated customer.

**Scopes**: `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_subscriptions.cancel(security: Models::Operations::CustomerPortalSubscriptionsCancelSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalSubscriptionsCancelSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                             | Type                                                                                                                                  | Required                                                                                                                              | Description                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                            | [Models::Operations::CustomerPortalSubscriptionsCancelSecurity](../../models/operations/customerportalsubscriptionscancelsecurity.md) | :heavy_check_mark:                                                                                                                    | The security requirements to use for the request.                                                                                     |
| `id`                                                                                                                                  | *::String*                                                                                                                            | :heavy_check_mark:                                                                                                                    | The subscription ID.                                                                                                                  |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsCancelResponse)](../../models/operations/customerportalsubscriptionscancelresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |