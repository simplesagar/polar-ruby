# Subscriptions
(*subscriptions*)

## Overview

### Available Operations

* [list](#list) - List Subscriptions
* [export](#export) - Export Subscriptions
* [get](#get) - Get Subscription
* [update](#update) - Update Subscription
* [revoke](#revoke) - Revoke Subscription

## list

List subscriptions.

**Scopes**: `subscriptions:read` `subscriptions:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::SubscriptionsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.subscriptions.list(req)

if ! res.list_resource_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `request`                                                                                           | [Models::Operations::SubscriptionsListRequest](../../models/operations/subscriptionslistrequest.md) | :heavy_check_mark:                                                                                  | The request object to use for the request.                                                          |

### Response

**[T.nilable(Models::Operations::SubscriptionsListResponse)](../../models/operations/subscriptionslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## export

Export subscriptions as a CSV file.

**Scopes**: `subscriptions:read` `subscriptions:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.subscriptions.export(organization_id=[
  "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
])

if ! res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `organization_id`                                                                           | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/organizationid.md) | :heavy_minus_sign:                                                                          | Filter by organization ID.                                                                  |

### Response

**[T.nilable(Models::Operations::SubscriptionsExportResponse)](../../models/operations/subscriptionsexportresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a subscription by ID.

**Scopes**: `subscriptions:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.subscriptions.get(id="<value>")

if ! res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `id`                 | *::String*           | :heavy_check_mark:   | The subscription ID. |

### Response

**[T.nilable(Models::Operations::SubscriptionsGetResponse)](../../models/operations/subscriptionsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a subscription.

**Scopes**: `subscriptions:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.subscriptions.update(id="<value>", subscription_update=Models::Shared::SubscriptionRevoke.new(
  revoke: false,
))

if ! res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                             | Type                                                                                                                                                                  | Required                                                                                                                                                              | Description                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                                                                  | *::String*                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                    | The subscription ID.                                                                                                                                                  |
| `subscription_update`                                                                                                                                                 | [T.any(Models::Shared::SubscriptionUpdateProduct, Models::Shared::SubscriptionCancel, Models::Shared::SubscriptionRevoke)](../../models/shared/subscriptionupdate.md) | :heavy_check_mark:                                                                                                                                                    | N/A                                                                                                                                                                   |

### Response

**[T.nilable(Models::Operations::SubscriptionsUpdateResponse)](../../models/operations/subscriptionsupdateresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |

## revoke

Revoke a subscription, i.e cancel immediately.

**Scopes**: `subscriptions:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.subscriptions.revoke(id="<value>")

if ! res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `id`                 | *::String*           | :heavy_check_mark:   | The subscription ID. |

### Response

**[T.nilable(Models::Operations::SubscriptionsRevokeResponse)](../../models/operations/subscriptionsrevokeresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |