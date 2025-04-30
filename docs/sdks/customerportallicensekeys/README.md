# CustomerPortalLicenseKeys
(*customer_portal_license_keys*)

## Overview

### Available Operations

* [list](#list) - List License Keys
* [get](#get) - Get License Key
* [validate](#validate) - Validate License Key
* [activate](#activate) - Activate License Key
* [deactivate](#deactivate) - Deactivate License Key

## list

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_license_keys.list(security: Models::Operations::CustomerPortalLicenseKeysListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalLicenseKeysListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), organization_id=[
  "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
], benefit_id="<value>", page=547_272, limit=678_317)

if ! res.list_resource_license_key_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                | Type                                                                                                                                     | Required                                                                                                                                 | Description                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                               | [Models::Operations::CustomerPortalLicenseKeysListSecurity](../../models/operations/customerportallicensekeyslistsecurity.md)            | :heavy_check_mark:                                                                                                                       | The security requirements to use for the request.                                                                                        |
| `organization_id`                                                                                                                        | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/customerportallicensekeyslistqueryparamorganizationidfilter.md) | :heavy_minus_sign:                                                                                                                       | Filter by organization ID.                                                                                                               |
| `benefit_id`                                                                                                                             | *T.nilable(::String)*                                                                                                                    | :heavy_minus_sign:                                                                                                                       | Filter by a specific benefit                                                                                                             |
| `page`                                                                                                                                   | *T.nilable(::Integer)*                                                                                                                   | :heavy_minus_sign:                                                                                                                       | Page number, defaults to 1.                                                                                                              |
| `limit`                                                                                                                                  | *T.nilable(::Integer)*                                                                                                                   | :heavy_minus_sign:                                                                                                                       | Size of a page, defaults to 10. Maximum is 100.                                                                                          |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysListResponse)](../../models/operations/customerportallicensekeyslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a license key.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_license_keys.get(security: Models::Operations::CustomerPortalLicenseKeysGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalLicenseKeysGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.license_key_with_activations.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                   | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                  | [Models::Operations::CustomerPortalLicenseKeysGetSecurity](../../models/operations/customerportallicensekeysgetsecurity.md) | :heavy_check_mark:                                                                                                          | The security requirements to use for the request.                                                                           |
| `id`                                                                                                                        | *::String*                                                                                                                  | :heavy_check_mark:                                                                                                          | N/A                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysGetResponse)](../../models/operations/customerportallicensekeysgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## validate

Validate a license key.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::LicenseKeyValidate.new(
  key: "<key>",
  organization_id: "<value>",
)

res = s.customer_portal_license_keys.validate(req)

if ! res.validated_license_key.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [Models::Shared::LicenseKeyValidate](../../models/shared/licensekeyvalidate.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysValidateResponse)](../../models/operations/customerportallicensekeysvalidateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## activate

Activate a license key instance.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::LicenseKeyActivate.new(
  key: "<key>",
  organization_id: "<value>",
  label: "<value>",
)

res = s.customer_portal_license_keys.activate(req)

if ! res.license_key_activation_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [Models::Shared::LicenseKeyActivate](../../models/shared/licensekeyactivate.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysActivateResponse)](../../models/operations/customerportallicensekeysactivateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## deactivate

Deactivate a license key instance.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::LicenseKeyDeactivate.new(
  key: "<key>",
  organization_id: "<value>",
  activation_id: "<value>",
)

res = s.customer_portal_license_keys.deactivate(req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `request`                                                                           | [Models::Shared::LicenseKeyDeactivate](../../models/shared/licensekeydeactivate.md) | :heavy_check_mark:                                                                  | The request object to use for the request.                                          |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysDeactivateResponse)](../../models/operations/customerportallicensekeysdeactivateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |