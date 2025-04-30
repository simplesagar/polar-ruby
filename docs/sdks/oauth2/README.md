# Oauth2
(*oauth2*)

## Overview

### Available Operations

* [authorize](#authorize) - Authorize
* [token](#token) - Request Token
* [revoke](#revoke) - Revoke Token
* [introspect](#introspect) - Introspect Token
* [userinfo](#userinfo) - Get User Info

## authorize

Authorize

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.oauth2.authorize()

if ! res.response_oauth2_authorize.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::Oauth2AuthorizeResponse)](../../models/operations/oauth2authorizeresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## token

Request an access token using a valid grant.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::AuthorizationCodeTokenRequest.new(
  grant_type: "<value>",
  client_id: "<id>",
  client_secret: "<value>",
  code: "<value>",
  redirect_uri: "https://old-fort.name",
)

res = s.oauth2.token(req)

if ! res.token_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                             | Type                                                                                                                                                  | Required                                                                                                                                              | Description                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                             | [T.any(Models::Shared::AuthorizationCodeTokenRequest, Models::Shared::RefreshTokenRequest)](../../models/operations/oauth2requesttokenrequestbody.md) | :heavy_check_mark:                                                                                                                                    | The request object to use for the request.                                                                                                            |

### Response

**[T.nilable(Models::Operations::Oauth2RequestTokenResponse)](../../models/operations/oauth2requesttokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## revoke

Revoke an access token or a refresh token.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::RevokeTokenRequest.new(
  token: "<value>",
  client_id: "<id>",
  client_secret: "<value>",
)

res = s.oauth2.revoke(req)

if ! res.revoke_token_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [Models::Shared::RevokeTokenRequest](../../models/shared/revoketokenrequest.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[T.nilable(Models::Operations::Oauth2RevokeTokenResponse)](../../models/operations/oauth2revoketokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## introspect

Get information about an access token.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::IntrospectTokenRequest.new(
  token: "<value>",
  client_id: "<id>",
  client_secret: "<value>",
)

res = s.oauth2.introspect(req)

if ! res.introspect_token_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `request`                                                                               | [Models::Shared::IntrospectTokenRequest](../../models/shared/introspecttokenrequest.md) | :heavy_check_mark:                                                                      | The request object to use for the request.                                              |

### Response

**[T.nilable(Models::Operations::Oauth2IntrospectTokenResponse)](../../models/operations/oauth2introspecttokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## userinfo

Get information about the authenticated user.

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.oauth2.userinfo()

if ! res.response_oauth2_userinfo.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::Oauth2UserinfoResponse)](../../models/operations/oauth2userinforesponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |