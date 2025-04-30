# Oauth2Clients
(*oauth2_clients*)

## Overview

### Available Operations

* [list](#list) - List Clients
* [create](#create) - Create Client
* [get](#get) - Get Client
* [update](#update) - Update Client
* [delete](#delete) - Delete Client

## list

List OAuth2 clients.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.oauth2_clients.list(page=768_578, limit=547_272)

if ! res.list_resource_o_auth2_client.nil?
  # handle response
end

```

### Parameters

| Parameter                                       | Type                                            | Required                                        | Description                                     |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `page`                                          | *T.nilable(::Integer)*                          | :heavy_minus_sign:                              | Page number, defaults to 1.                     |
| `limit`                                         | *T.nilable(::Integer)*                          | :heavy_minus_sign:                              | Size of a page, defaults to 10. Maximum is 100. |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsListResponse)](../../models/operations/oauth2clientslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create an OAuth2 client.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::OAuth2ClientConfiguration.new(
  redirect_uris: [
    "https://probable-heating.com/",
  ],
  client_name: "<value>",
)

res = s.oauth2_clients.create(req)

if ! res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `request`                                                                                     | [Models::Shared::OAuth2ClientConfiguration](../../models/shared/oauth2clientconfiguration.md) | :heavy_check_mark:                                                                            | The request object to use for the request.                                                    |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2CreateClientResponse)](../../models/operations/oauth2clientsoauth2createclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an OAuth2 client by Client ID.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.oauth2_clients.get(client_id="<id>")

if ! res.any.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `client_id`        | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2GetClientResponse)](../../models/operations/oauth2clientsoauth2getclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update an OAuth2 client.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.oauth2_clients.update(client_id="<id>", o_auth2_client_configuration_update=Models::Shared::OAuth2ClientConfigurationUpdate.new(
  redirect_uris: [
    "https://passionate-flu.org",
  ],
  client_name: "<value>",
  client_id: "<id>",
))

if ! res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                 | Type                                                                                                      | Required                                                                                                  | Description                                                                                               |
| --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `client_id`                                                                                               | *::String*                                                                                                | :heavy_check_mark:                                                                                        | N/A                                                                                                       |
| `o_auth2_client_configuration_update`                                                                     | [Models::Shared::OAuth2ClientConfigurationUpdate](../../models/shared/oauth2clientconfigurationupdate.md) | :heavy_check_mark:                                                                                        | N/A                                                                                                       |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2UpdateClientResponse)](../../models/operations/oauth2clientsoauth2updateclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete an OAuth2 client.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.oauth2_clients.delete(client_id="<id>")

if ! res.any.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `client_id`        | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2DeleteClientResponse)](../../models/operations/oauth2clientsoauth2deleteclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |