# Meters
(*meters*)

## Overview

### Available Operations

* [list](#list) - List Meters
* [create](#create) - Create Meter
* [get](#get) - Get Meter
* [update](#update) - Update Meter
* [quantities](#quantities) - Get Meter Quantities

## list

List meters.

**Scopes**: `meters:read` `meters:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::MetersListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.meters.list(req)

if ! res.list_resource_meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Operations::MetersListRequest](../../models/operations/meterslistrequest.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::MetersListResponse)](../../models/operations/meterslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a meter.

**Scopes**: `meters:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::MeterCreate.new(
  name: "<value>",
  filter: Models::Shared::Filter.new(
    conjunction: Models::Shared::FilterConjunction::AND,
    clauses: [],
  ),
  aggregation: Models::Shared::PropertyAggregation.new(
    func: Models::Shared::Func::MAX,
    property: "<value>",
  ),
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
)

res = s.meters.create(req)

if ! res.meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `request`                                                         | [Models::Shared::MeterCreate](../../models/shared/metercreate.md) | :heavy_check_mark:                                                | The request object to use for the request.                        |

### Response

**[T.nilable(Models::Operations::MetersCreateResponse)](../../models/operations/meterscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a meter by ID.

**Scopes**: `meters:read` `meters:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.meters.get(id="<value>")

if ! res.meter.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The meter ID.      |

### Response

**[T.nilable(Models::Operations::MetersGetResponse)](../../models/operations/metersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a meter.

**Scopes**: `meters:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.meters.update(id="<value>", meter_update=Models::Shared::MeterUpdate.new())

if ! res.meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `id`                                                              | *::String*                                                        | :heavy_check_mark:                                                | The meter ID.                                                     |
| `meter_update`                                                    | [Models::Shared::MeterUpdate](../../models/shared/meterupdate.md) | :heavy_check_mark:                                                | N/A                                                               |

### Response

**[T.nilable(Models::Operations::MetersUpdateResponse)](../../models/operations/metersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## quantities

Get quantities of a meter over a time period.

**Scopes**: `meters:read` `meters:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::MetersQuantitiesRequest.new(
  id: "<value>",
  start_timestamp: DateTime.iso8601('2023-09-17T00:45:34.608Z'),
  end_timestamp: DateTime.iso8601('2023-07-21T18:11:39.069Z'),
  interval: Models::Shared::TimeInterval::HOUR,
)

res = s.meters.quantities(req)

if ! res.meter_quantities.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `request`                                                                                         | [Models::Operations::MetersQuantitiesRequest](../../models/operations/metersquantitiesrequest.md) | :heavy_check_mark:                                                                                | The request object to use for the request.                                                        |

### Response

**[T.nilable(Models::Operations::MetersQuantitiesResponse)](../../models/operations/metersquantitiesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |