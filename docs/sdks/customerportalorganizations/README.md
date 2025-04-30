# CustomerPortalOrganizations
(*customer_portal_organizations*)

## Overview

### Available Operations

* [get](#get) - Get Organization

## get

Get a customer portal's organization by slug.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.customer_portal_organizations.get(slug="<value>")

if ! res.customer_organization.nil?
  # handle response
end

```

### Parameters

| Parameter              | Type                   | Required               | Description            |
| ---------------------- | ---------------------- | ---------------------- | ---------------------- |
| `slug`                 | *::String*             | :heavy_check_mark:     | The organization slug. |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrganizationsGetResponse)](../../models/operations/customerportalorganizationsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |