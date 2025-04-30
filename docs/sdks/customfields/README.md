# CustomFields
(*custom_fields*)

## Overview

### Available Operations

* [list](#list) - List Custom Fields
* [create](#create) - Create Custom Field
* [get](#get) - Get Custom Field
* [update](#update) - Update Custom Field
* [delete](#delete) - Delete Custom Field

## list

List custom fields.

**Scopes**: `custom_fields:read` `custom_fields:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Operations::CustomFieldsListRequest.new(
  organization_id: [
    "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  ],
)

res = s.custom_fields.list(req)

if ! res.list_resource_custom_field.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `request`                                                                                         | [Models::Operations::CustomFieldsListRequest](../../models/operations/customfieldslistrequest.md) | :heavy_check_mark:                                                                                | The request object to use for the request.                                                        |

### Response

**[T.nilable(Models::Operations::CustomFieldsListResponse)](../../models/operations/customfieldslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a custom field.

**Scopes**: `custom_fields:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::CustomFieldCreateNumber.new(
  type: "<value>",
  slug: "<value>",
  name: "<value>",
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  properties: Models::Shared::CustomFieldNumberProperties.new(),
)

res = s.custom_fields.create(req)

if ! res.custom_field.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                    | Type                                                                                                                                                                                                                                                         | Required                                                                                                                                                                                                                                                     | Description                                                                                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                                                                                                    | [T.any(Models::Shared::CustomFieldCreateText, Models::Shared::CustomFieldCreateNumber, Models::Shared::CustomFieldCreateDate, Models::Shared::CustomFieldCreateCheckbox, Models::Shared::CustomFieldCreateSelect)](../../models/shared/customfieldcreate.md) | :heavy_check_mark:                                                                                                                                                                                                                                           | The request object to use for the request.                                                                                                                                                                                                                   |

### Response

**[T.nilable(Models::Operations::CustomFieldsCreateResponse)](../../models/operations/customfieldscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a custom field by ID.

**Scopes**: `custom_fields:read` `custom_fields:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.custom_fields.get(id="<value>")

if ! res.custom_field.nil?
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `id`                 | *::String*           | :heavy_check_mark:   | The custom field ID. |

### Response

**[T.nilable(Models::Operations::CustomFieldsGetResponse)](../../models/operations/customfieldsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a custom field.

**Scopes**: `custom_fields:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.custom_fields.update(id="<value>", custom_field_update=Models::Shared::CustomFieldUpdateText.new(
  type: "<value>",
))

if ! res.custom_field.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                    | Type                                                                                                                                                                                                                                                         | Required                                                                                                                                                                                                                                                     | Description                                                                                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                                                                                                                                                                         | *::String*                                                                                                                                                                                                                                                   | :heavy_check_mark:                                                                                                                                                                                                                                           | The custom field ID.                                                                                                                                                                                                                                         |
| `custom_field_update`                                                                                                                                                                                                                                        | [T.any(Models::Shared::CustomFieldUpdateText, Models::Shared::CustomFieldUpdateNumber, Models::Shared::CustomFieldUpdateDate, Models::Shared::CustomFieldUpdateCheckbox, Models::Shared::CustomFieldUpdateSelect)](../../models/shared/customfieldupdate.md) | :heavy_check_mark:                                                                                                                                                                                                                                           | N/A                                                                                                                                                                                                                                                          |

### Response

**[T.nilable(Models::Operations::CustomFieldsUpdateResponse)](../../models/operations/customfieldsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a custom field.

**Scopes**: `custom_fields:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.custom_fields.delete(id="<value>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `id`                 | *::String*           | :heavy_check_mark:   | The custom field ID. |

### Response

**[T.nilable(Models::Operations::CustomFieldsDeleteResponse)](../../models/operations/customfieldsdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |