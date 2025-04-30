# LicenseKeys
(*license_keys*)

## Overview

### Available Operations

* [list](#list) - List License Keys
* [get](#get) - Get License Key
* [update](#update) - Update License Key
* [get_activation](#get_activation) - Get Activation

## list

Get license keys connected to the given organization & filters.

**Scopes**: `license_keys:read` `license_keys:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.license_keys.list(organization_id=[
  "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
], benefit_id=[
  "<value>",
], page=678_317, limit=177_706)

if ! res.list_resource_license_key_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                  | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                                          | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/licensekeyslistqueryparamorganizationidfilter.md) | :heavy_minus_sign:                                                                                                         | Filter by organization ID.                                                                                                 |
| `benefit_id`                                                                                                               | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/queryparambenefitidfilter.md)                     | :heavy_minus_sign:                                                                                                         | Filter by benefit ID.                                                                                                      |
| `page`                                                                                                                     | *T.nilable(::Integer)*                                                                                                     | :heavy_minus_sign:                                                                                                         | Page number, defaults to 1.                                                                                                |
| `limit`                                                                                                                    | *T.nilable(::Integer)*                                                                                                     | :heavy_minus_sign:                                                                                                         | Size of a page, defaults to 10. Maximum is 100.                                                                            |

### Response

**[T.nilable(Models::Operations::LicenseKeysListResponse)](../../models/operations/licensekeyslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a license key.

**Scopes**: `license_keys:read` `license_keys:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.license_keys.get(id="<value>")

if ! res.license_key_with_activations.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::LicenseKeysGetResponse)](../../models/operations/licensekeysgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a license key.

**Scopes**: `license_keys:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.license_keys.update(id="<value>", license_key_update=Models::Shared::LicenseKeyUpdate.new())

if ! res.license_key_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `id`                                                                        | *::String*                                                                  | :heavy_check_mark:                                                          | N/A                                                                         |
| `license_key_update`                                                        | [Models::Shared::LicenseKeyUpdate](../../models/shared/licensekeyupdate.md) | :heavy_check_mark:                                                          | N/A                                                                         |

### Response

**[T.nilable(Models::Operations::LicenseKeysUpdateResponse)](../../models/operations/licensekeysupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_activation

Get a license key activation.

**Scopes**: `license_keys:read` `license_keys:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.license_keys.get_activation(id="<value>", activation_id="<value>")

if ! res.license_key_activation_read.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |
| `activation_id`    | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::LicenseKeysGetActivationResponse)](../../models/operations/licensekeysgetactivationresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |