<!-- Start SDK Example Usage [usage] -->
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
<!-- End SDK Example Usage [usage] -->