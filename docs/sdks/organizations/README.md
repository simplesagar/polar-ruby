# Organizations
(*organizations*)

## Overview

### Available Operations

* [list](#list) - List Organizations
* [create](#create) - Create Organization
* [get](#get) - Get Organization
* [update](#update) - Update Organization

## list

List organizations.

**Scopes**: `organizations:read` `organizations:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.organizations.list(slug="<value>", page=768_578, limit=547_272, sorting=[
  Models::Shared::OrganizationSortProperty::NAME,
])

if ! res.list_resource_organization.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                               | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `slug`                                                                                                                                                                  | *T.nilable(::String)*                                                                                                                                                   | :heavy_minus_sign:                                                                                                                                                      | Filter by slug.                                                                                                                                                         |
| `page`                                                                                                                                                                  | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Page number, defaults to 1.                                                                                                                                             |
| `limit`                                                                                                                                                                 | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Size of a page, defaults to 10. Maximum is 100.                                                                                                                         |
| `sorting`                                                                                                                                                               | T::Array<[Models::Shared::OrganizationSortProperty](../../models/shared/organizationsortproperty.md)>                                                                   | :heavy_minus_sign:                                                                                                                                                      | Sorting criterion. Several criteria can be used simultaneously and will be applied in order. Add a minus sign `-` before the criteria name to sort by descending order. |

### Response

**[T.nilable(Models::Operations::OrganizationsListResponse)](../../models/operations/organizationslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create an organization.

**Scopes**: `organizations:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::OrganizationCreate.new(
  name: "<value>",
  slug: "<value>",
)

res = s.organizations.create(req)

if ! res.organization.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [Models::Shared::OrganizationCreate](../../models/shared/organizationcreate.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[T.nilable(Models::Operations::OrganizationsCreateResponse)](../../models/operations/organizationscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an organization by ID.

**Scopes**: `organizations:read` `organizations:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.organizations.get(id="1dbfc517-0bbf-4301-9ba8-555ca42b9737")

if ! res.organization.nil?
  # handle response
end

```

### Parameters

| Parameter                            | Type                                 | Required                             | Description                          | Example                              |
| ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ |
| `id`                                 | *::String*                           | :heavy_check_mark:                   | N/A                                  | 1dbfc517-0bbf-4301-9ba8-555ca42b9737 |

### Response

**[T.nilable(Models::Operations::OrganizationsGetResponse)](../../models/operations/organizationsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update an organization.

**Scopes**: `organizations:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.organizations.update(id="1dbfc517-0bbf-4301-9ba8-555ca42b9737", organization_update=Models::Shared::OrganizationUpdate.new())

if ! res.organization.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     | Example                                                                         |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `id`                                                                            | *::String*                                                                      | :heavy_check_mark:                                                              | N/A                                                                             | 1dbfc517-0bbf-4301-9ba8-555ca42b9737                                            |
| `organization_update`                                                           | [Models::Shared::OrganizationUpdate](../../models/shared/organizationupdate.md) | :heavy_check_mark:                                                              | N/A                                                                             |                                                                                 |

### Response

**[T.nilable(Models::Operations::OrganizationsUpdateResponse)](../../models/operations/organizationsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |