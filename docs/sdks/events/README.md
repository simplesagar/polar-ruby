# Events
(*events*)

## Overview

### Available Operations

* [list](#list) - List Events
* [list_names](#list_names) - List Event Names
* [get](#get) - Get Event
* [ingest](#ingest) - Ingest Events

## list

List events.

**Scopes**: `events:read` `events:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::EventsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.events.list(req)

if ! res.list_resource_event.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Operations::EventsListRequest](../../models/operations/eventslistrequest.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::EventsListResponse)](../../models/operations/eventslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_names

List event names.

**Scopes**: `events:read` `events:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::EventsListNamesRequest.new(
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
)

res = s.events.list_names(req)

if ! res.list_resource_event_name.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                       | Type                                                                                            | Required                                                                                        | Description                                                                                     |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `request`                                                                                       | [Models::Operations::EventsListNamesRequest](../../models/operations/eventslistnamesrequest.md) | :heavy_check_mark:                                                                              | The request object to use for the request.                                                      |

### Response

**[T.nilable(Models::Operations::EventsListNamesResponse)](../../models/operations/eventslistnamesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an event by ID.

**Scopes**: `events:read` `events:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.events.get(id="<value>")

if ! res.event.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The event ID.      |

### Response

**[T.nilable(Models::Operations::EventsGetResponse)](../../models/operations/eventsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## ingest

Ingest batch of events.

**Scopes**: `events:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::EventsIngest.new(
  events: [
    Models::Shared::EventCreateExternalCustomer.new(
      name: "<value>",
      organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
      external_customer_id: "<id>",
    ),
  ],
)

res = s.events.ingest(req)

if ! res.events_ingest_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [Models::Shared::EventsIngest](../../models/shared/eventsingest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[T.nilable(Models::Operations::EventsIngestResponse)](../../models/operations/eventsingestresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |