# Metrics
(*metrics*)

## Overview

### Available Operations

* [get](#get) - Get Metrics
* [limits](#limits) - Get Metrics Limits

## get

Get metrics about your orders and subscriptions.

Currency values are output in cents.

**Scopes**: `metrics:read`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::MetricsGetRequest.new(
  start_date: Date.parse("2025-02-06"),
  end_date: Date.parse("2024-09-04"),
  interval: Models::Shared::TimeInterval::WEEK,
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.metrics.get(req)

if ! res.metrics_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Operations::MetricsGetRequest](../../models/operations/metricsgetrequest.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::MetricsGetResponse)](../../models/operations/metricsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## limits

Get the interval limits for the metrics endpoint.

**Scopes**: `metrics:read`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.metrics.limits()

if ! res.metrics_limits.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::MetricsLimitsResponse)](../../models/operations/metricslimitsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |