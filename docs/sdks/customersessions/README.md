# CustomerSessions
(*customer_sessions*)

## Overview

### Available Operations

* [create](#create) - Create Customer Session

## create

Create a customer session.

**Scopes**: `customer_sessions:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::CustomerSessionCustomerIDCreate.new(
  customer_id: "<value>",
)

res = s.customer_sessions.create(req)

if ! res.customer_session.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                 | Type                                                                                                                                                                                      | Required                                                                                                                                                                                  | Description                                                                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                 | [T.any(Models::Shared::CustomerSessionCustomerIDCreate, Models::Shared::CustomerSessionCustomerExternalIDCreate)](../../models/operations/customersessionscreatecustomersessioncreate.md) | :heavy_check_mark:                                                                                                                                                                        | The request object to use for the request.                                                                                                                                                |

### Response

**[T.nilable(Models::Operations::CustomerSessionsCreateResponse)](../../models/operations/customersessionscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |