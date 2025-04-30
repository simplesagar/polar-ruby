# CustomerPortalBenefitGrants
(*customer_portal_benefit_grants*)

## Overview

### Available Operations

* [list](#list) - List Benefit Grants
* [get](#get) - Get Benefit Grant
* [update](#update) - Update Benefit Grant

## list

List benefits grants of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Operations::CustomerPortalBenefitGrantsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.customer_portal_benefit_grants.list(security: Models::Operations::CustomerPortalBenefitGrantsListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), req, Models::Operations::CustomerPortalBenefitGrantsListSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ))

if ! res.list_resource_customer_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                         | Type                                                                                                                              | Required                                                                                                                          | Description                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                         | [Models::Operations::CustomerPortalBenefitGrantsListRequest](../../models/operations/customerportalbenefitgrantslistrequest.md)   | :heavy_check_mark:                                                                                                                | The request object to use for the request.                                                                                        |
| `security`                                                                                                                        | [Models::Operations::CustomerPortalBenefitGrantsListSecurity](../../models/operations/customerportalbenefitgrantslistsecurity.md) | :heavy_check_mark:                                                                                                                | The security requirements to use for the request.                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalBenefitGrantsListResponse)](../../models/operations/customerportalbenefitgrantslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a benefit grant by ID for the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_benefit_grants.get(security: Models::Operations::CustomerPortalBenefitGrantsGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalBenefitGrantsGetSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>")

if ! res.customer_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                       | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                      | [Models::Operations::CustomerPortalBenefitGrantsGetSecurity](../../models/operations/customerportalbenefitgrantsgetsecurity.md) | :heavy_check_mark:                                                                                                              | The security requirements to use for the request.                                                                               |
| `id`                                                                                                                            | *::String*                                                                                                                      | :heavy_check_mark:                                                                                                              | The benefit grant ID.                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalBenefitGrantsGetResponse)](../../models/operations/customerportalbenefitgrantsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a benefit grant for the authenticated customer.

**Scopes**: `customer_portal:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

res = s.customer_portal_benefit_grants.update(security: Models::Operations::CustomerPortalBenefitGrantsUpdateSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), Models::Operations::CustomerPortalBenefitGrantsUpdateSecurity.new(
    customer_session: "<YOUR_BEARER_TOKEN_HERE>",
  ), id="<value>", customer_benefit_grant_update=Models::Shared::CustomerBenefitGrantMeterCreditUpdate.new(
  benefit_type: "<value>",
))

if ! res.customer_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                                                                                                                                                          | Type                                                                                                                                                                                                                                                                                                                                                                                               | Required                                                                                                                                                                                                                                                                                                                                                                                           | Description                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                                                                                                                                                                                                                                         | [Models::Operations::CustomerPortalBenefitGrantsUpdateSecurity](../../models/operations/customerportalbenefitgrantsupdatesecurity.md)                                                                                                                                                                                                                                                              | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                                                 | The security requirements to use for the request.                                                                                                                                                                                                                                                                                                                                                  |
| `id`                                                                                                                                                                                                                                                                                                                                                                                               | *::String*                                                                                                                                                                                                                                                                                                                                                                                         | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                                                 | The benefit grant ID.                                                                                                                                                                                                                                                                                                                                                                              |
| `customer_benefit_grant_update`                                                                                                                                                                                                                                                                                                                                                                    | [T.any(Models::Shared::CustomerBenefitGrantDiscordUpdate, Models::Shared::CustomerBenefitGrantGitHubRepositoryUpdate, Models::Shared::CustomerBenefitGrantDownloadablesUpdate, Models::Shared::CustomerBenefitGrantLicenseKeysUpdate, Models::Shared::CustomerBenefitGrantCustomUpdate, Models::Shared::CustomerBenefitGrantMeterCreditUpdate)](../../models/shared/customerbenefitgrantupdate.md) | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                                                 | N/A                                                                                                                                                                                                                                                                                                                                                                                                |

### Response

**[T.nilable(Models::Operations::CustomerPortalBenefitGrantsUpdateResponse)](../../models/operations/customerportalbenefitgrantsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |