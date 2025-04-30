# CustomerPortalDownloadables
(*customer_portal_downloadables*)

## Overview

### Available Operations

* [list](#list) - List Downloadables
* [get](#get) - Get Downloadable

## list

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_downloadables.list(security: Models::Operations::CustomerPortalDownloadablesListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalDownloadablesListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), organization_id=[
  "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
], benefit_id=[
  "<value>",
], page=678_317, limit=177_706)

if ! res.list_resource_downloadable_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                  | Type                                                                                                                                       | Required                                                                                                                                   | Description                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `security`                                                                                                                                 | [Models::Operations::CustomerPortalDownloadablesListSecurity](../../models/operations/customerportaldownloadableslistsecurity.md)          | :heavy_check_mark:                                                                                                                         | The security requirements to use for the request.                                                                                          |
| `organization_id`                                                                                                                          | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/customerportaldownloadableslistqueryparamorganizationidfilter.md) | :heavy_minus_sign:                                                                                                                         | Filter by organization ID.                                                                                                                 |
| `benefit_id`                                                                                                                               | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/customerportaldownloadableslistqueryparambenefitidfilter.md)      | :heavy_minus_sign:                                                                                                                         | Filter by benefit ID.                                                                                                                      |
| `page`                                                                                                                                     | *T.nilable(::Integer)*                                                                                                                     | :heavy_minus_sign:                                                                                                                         | Page number, defaults to 1.                                                                                                                |
| `limit`                                                                                                                                    | *T.nilable(::Integer)*                                                                                                                     | :heavy_minus_sign:                                                                                                                         | Size of a page, defaults to 10. Maximum is 100.                                                                                            |

### Response

**[T.nilable(Models::Operations::CustomerPortalDownloadablesListResponse)](../../models/operations/customerportaldownloadableslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get Downloadable

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_downloadables.get(token="<value>")

if ! res.any.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `token`            | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CustomerPortalDownloadablesCustomerPortalDownloadablesGetResponse)](../../models/operations/customerportaldownloadablescustomerportaldownloadablesgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |