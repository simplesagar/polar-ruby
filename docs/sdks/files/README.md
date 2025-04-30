# Files
(*files*)

## Overview

### Available Operations

* [list](#list) - List Files
* [create](#create) - Create File
* [uploaded](#uploaded) - Complete File Upload
* [update](#update) - Update File
* [delete](#delete) - Delete File

## list

List files.

**Scopes**: `files:read` `files:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.files.list(organization_id="1dbfc517-0bbf-4301-9ba8-555ca42b9737", ids=[
  "<value>",
], page=768_578, limit=547_272)

if ! res.list_resource_file_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                       | Type                                            | Required                                        | Description                                     | Example                                         |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `organization_id`                               | *T.nilable(::String)*                           | :heavy_minus_sign:                              | N/A                                             | 1dbfc517-0bbf-4301-9ba8-555ca42b9737            |
| `ids`                                           | T::Array<*::String*>                            | :heavy_minus_sign:                              | List of file IDs to get.                        |                                                 |
| `page`                                          | *T.nilable(::Integer)*                          | :heavy_minus_sign:                              | Page number, defaults to 1.                     |                                                 |
| `limit`                                         | *T.nilable(::Integer)*                          | :heavy_minus_sign:                              | Size of a page, defaults to 10. Maximum is 100. |                                                 |

### Response

**[T.nilable(Models::Operations::FilesListResponse)](../../models/operations/fileslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a file.

**Scopes**: `files:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

req = Models::Shared::OrganizationAvatarFileCreate.new(
  organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
  name: "<value>",
  mime_type: "<value>",
  size: 638_424,
  upload: Models::Shared::S3FileCreateMultipart.new(
    parts: [
      Models::Shared::S3FileCreatePart.new(
        number: 417_458,
        chunk_start: 134_365,
        chunk_end: 69_025,
      ),
    ],
  ),
  service: "<value>",
)

res = s.files.create(req)

if ! res.file_upload.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                | Type                                                                                                                                                                     | Required                                                                                                                                                                 | Description                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                | [T.any(Models::Shared::DownloadableFileCreate, Models::Shared::ProductMediaFileCreate, Models::Shared::OrganizationAvatarFileCreate)](../../models/shared/filecreate.md) | :heavy_check_mark:                                                                                                                                                       | The request object to use for the request.                                                                                                                               |

### Response

**[T.nilable(Models::Operations::FilesCreateResponse)](../../models/operations/filescreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## uploaded

Complete a file upload.

**Scopes**: `files:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.files.uploaded(id="<value>", file_upload_completed=Models::Shared::FileUploadCompleted.new(
  id: "<id>",
  path: "/sys",
  parts: [
    Models::Shared::S3FileUploadCompletedPart.new(
      number: 848_922,
      checksum_etag: "<value>",
      checksum_sha256_base64: "<value>",
    ),
  ],
))

if ! res.response_files_uploaded.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `id`                                                                              | *::String*                                                                        | :heavy_check_mark:                                                                | The file ID.                                                                      |
| `file_upload_completed`                                                           | [Models::Shared::FileUploadCompleted](../../models/shared/fileuploadcompleted.md) | :heavy_check_mark:                                                                | N/A                                                                               |

### Response

**[T.nilable(Models::Operations::FilesUploadedResponse)](../../models/operations/filesuploadedresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a file.

**Scopes**: `files:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.files.update(id="<value>", file_patch=Models::Shared::FilePatch.new())

if ! res.response_files_update.nil?
  # handle response
end

```

### Parameters

| Parameter                                                     | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `id`                                                          | *::String*                                                    | :heavy_check_mark:                                            | The file ID.                                                  |
| `file_patch`                                                  | [Models::Shared::FilePatch](../../models/shared/filepatch.md) | :heavy_check_mark:                                            | N/A                                                           |

### Response

**[T.nilable(Models::Operations::FilesUpdateResponse)](../../models/operations/filesupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a file.

**Scopes**: `files:write`

### Example Usage

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.files.delete(id="<value>")

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::FilesDeleteResponse)](../../models/operations/filesdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |