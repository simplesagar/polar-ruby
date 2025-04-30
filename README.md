# polar-sdk

Developer-friendly & type-safe Ruby SDK specifically catered to leverage *polar-sdk* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=polar-sdk&utm_campaign=ruby"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20Speakeasy-212015?style=for-the-badge&logoColor=FBE331&logo=speakeasy&labelColor=545454" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/sagar-demo/sagar-demo). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Polar API: Polar HTTP and Webhooks API

Read the docs at https://docs.polar.sh/api-reference
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [polar-sdk](#polar-sdk)
  * [SDK Installation](#sdk-installation)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed using [RubyGems](https://rubygems.org/):

```bash
gem install specific_install
gem specific_install  
```
<!-- End SDK Installation [installation] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new

req = Models::Shared::WebhookCheckoutCreatedPayload.new(
  type: "checkout.created",
  data: Models::Shared::Checkout.new(
    created_at: DateTime.iso8601('2025-11-12T14:26:42.882Z'),
    modified_at: DateTime.iso8601('2024-05-27T05:08:06.235Z'),
    id: "<value>",
    payment_processor: Models::Shared::PaymentProcessor::STRIPE,
    status: Models::Shared::CheckoutStatus::FAILED,
    client_secret: "<value>",
    url: "https://heavy-beret.com/",
    expires_at: DateTime.iso8601('2023-02-25T02:26:48.460Z'),
    success_url: "https://sardonic-final.info/",
    embed_origin: "<value>",
    amount: 962_818,
    discount_amount: 6400,
    net_amount: 426_090,
    tax_amount: 648_726,
    total_amount: 210_702,
    currency: "Riel",
    product_id: "<value>",
    product_price_id: "<value>",
    discount_id: "<value>",
    allow_discount_codes: false,
    require_billing_address: false,
    is_discount_applicable: false,
    is_free_product_price: false,
    is_payment_required: false,
    is_payment_setup_required: false,
    is_payment_form_required: false,
    customer_id: "<value>",
    customer_name: "<value>",
    customer_email: "<value>",
    customer_ip_address: "<value>",
    customer_billing_address: Models::Shared::Address.new(
      country: "FR",
    ),
    customer_tax_id: "<id>",
    payment_processor_metadata: {
      "key": "<value>",
    },
    metadata: {
      "key": 5003.72,
    },
    customer_external_id: "<id>",
    products: [
      Models::Shared::CheckoutProduct.new(
        created_at: DateTime.iso8601('2025-01-24T18:08:49.597Z'),
        modified_at: DateTime.iso8601('2025-07-22T12:18:02.066Z'),
        id: "<value>",
        name: "<value>",
        description: "gosh really capitalize um restructure prickly rationale certainly these",
        recurring_interval: Models::Shared::SubscriptionRecurringInterval::YEAR,
        is_recurring: false,
        is_archived: false,
        organization_id: "<value>",
        prices: [
          Models::Shared::ProductPriceFixed.new(
            created_at: DateTime.iso8601('2025-08-22T02:17:20.661Z'),
            modified_at: DateTime.iso8601('2025-09-12T19:41:14.261Z'),
            id: "<value>",
            amount_type: "<value>",
            is_archived: false,
            product_id: "<value>",
            type: Models::Shared::ProductPriceType::ONE_TIME,
            recurring_interval: Models::Shared::SubscriptionRecurringInterval::YEAR,
            price_currency: "<value>",
            price_amount: 991_185,
          ),
        ],
        benefits: [
          Models::Shared::BenefitPublic.new(
            id: "<value>",
            created_at: DateTime.iso8601('2024-06-16T08:01:15.524Z'),
            modified_at: DateTime.iso8601('2025-06-29T02:23:28.661Z'),
            type: Models::Shared::BenefitType::GITHUB_REPOSITORY,
            description: "provided publicize astride oof mockingly if opposite coagulate pro",
            selectable: false,
            deletable: false,
            organization_id: "<value>",
          ),
        ],
        medias: [
          Models::Shared::ProductMediaFileRead.new(
            id: "<value>",
            organization_id: "<value>",
            name: "<value>",
            path: "/opt/lib",
            mime_type: "<value>",
            size: 877_199,
            storage_version: "<value>",
            checksum_etag: "<value>",
            checksum_sha256_base64: "<value>",
            checksum_sha256_hex: "<value>",
            last_modified_at: DateTime.iso8601('2024-12-28T06:38:59.235Z'),
            version: "<value>",
            service: "<value>",
            is_uploaded: false,
            created_at: DateTime.iso8601('2025-12-23T03:24:50.631Z'),
            size_readable: "<value>",
            public_url: "https://inconsequential-tenement.net/",
          ),
        ],
      ),
    ],
    product: Models::Shared::CheckoutProduct.new(
      created_at: DateTime.iso8601('2025-03-11T01:07:03.723Z'),
      modified_at: DateTime.iso8601('2023-07-06T04:03:30.465Z'),
      id: "<value>",
      name: "<value>",
      description: "but reluctantly easily litter",
      recurring_interval: Models::Shared::SubscriptionRecurringInterval::YEAR,
      is_recurring: false,
      is_archived: false,
      organization_id: "<value>",
      prices: [
        Models::Shared::ProductPriceFree.new(
          created_at: DateTime.iso8601('2024-02-10T10:32:57.489Z'),
          modified_at: DateTime.iso8601('2024-07-14T23:53:19.831Z'),
          id: "<value>",
          amount_type: "<value>",
          is_archived: false,
          product_id: "<value>",
          type: Models::Shared::ProductPriceType::ONE_TIME,
          recurring_interval: Models::Shared::SubscriptionRecurringInterval::YEAR,
        ),
      ],
      benefits: [
        Models::Shared::BenefitPublic.new(
          id: "<value>",
          created_at: DateTime.iso8601('2025-03-02T02:06:06.947Z'),
          modified_at: DateTime.iso8601('2024-01-11T18:56:38.677Z'),
          type: Models::Shared::BenefitType::METER_CREDIT,
          description: "offensively painfully what questionably destock pish ironclad",
          selectable: false,
          deletable: false,
          organization_id: "<value>",
        ),
      ],
      medias: [
        Models::Shared::ProductMediaFileRead.new(
          id: "<value>",
          organization_id: "<value>",
          name: "<value>",
          path: "/usr/bin",
          mime_type: "<value>",
          size: 721_205,
          storage_version: "<value>",
          checksum_etag: "<value>",
          checksum_sha256_base64: "<value>",
          checksum_sha256_hex: "<value>",
          last_modified_at: DateTime.iso8601('2024-03-02T18:57:38.880Z'),
          version: "<value>",
          service: "<value>",
          is_uploaded: false,
          created_at: DateTime.iso8601('2024-09-21T20:33:41.052Z'),
          size_readable: "<value>",
          public_url: "https://sardonic-cannon.org/",
        ),
      ],
    ),
    product_price: Models::Shared::LegacyRecurringProductPriceFree.new(
      created_at: DateTime.iso8601('2023-01-13T03:58:12.376Z'),
      modified_at: DateTime.iso8601('2025-02-04T17:46:21.813Z'),
      id: "<value>",
      amount_type: "<value>",
      is_archived: false,
      product_id: "<value>",
      type: "<value>",
      recurring_interval: Models::Shared::SubscriptionRecurringInterval::MONTH,
      legacy: false,
    ),
    discount: Models::Shared::CheckoutDiscountPercentageOnceForeverDuration.new(
      duration: Models::Shared::DiscountDuration::FOREVER,
      type: Models::Shared::DiscountType::PERCENTAGE,
      basis_points: 247_960,
      id: "<value>",
      name: "<value>",
      code: "<value>",
    ),
    subscription_id: "<value>",
    attached_custom_fields: [
      Models::Shared::AttachedCustomField.new(
        custom_field_id: "<value>",
        custom_field: Models::Shared::CustomFieldDate.new(
          created_at: DateTime.iso8601('2025-03-29T02:39:20.427Z'),
          modified_at: DateTime.iso8601('2024-05-17T17:07:35.182Z'),
          id: "<value>",
          metadata: {
            "key": 548_991,
          },
          type: "<value>",
          slug: "<value>",
          name: "<value>",
          organization_id: "1dbfc517-0bbf-4301-9ba8-555ca42b9737",
          properties: Models::Shared::CustomFieldDateProperties.new(),
        ),
        order: 907_325,
        required: false,
      ),
    ],
    customer_metadata: {
      "key": "<value>",
    },
    customer_billing_address_fields: Models::Shared::CheckoutCustomerBillingAddressFields.new(
      country: false,
      state: false,
      city: false,
      postal_code: false,
      line1: false,
      line2: false,
    ),
  ),
)

res = s.endpointcheckout_created_post(req)

if ! res.any.nil?
  # handle response
end

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name           | Type | Scheme      |
| -------------- | ---- | ----------- |
| `access_token` | http | HTTP Bearer |

To authenticate with the API the `access_token` parameter must be set when initializing the SDK client instance. For example:
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

### Per-Operation Security Schemes

Some operations in this SDK require the security scheme to be specified at the request level. For example:
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
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [benefits](docs/sdks/benefits/README.md)

* [list](docs/sdks/benefits/README.md#list) - List Benefits
* [create](docs/sdks/benefits/README.md#create) - Create Benefit
* [get](docs/sdks/benefits/README.md#get) - Get Benefit
* [update](docs/sdks/benefits/README.md#update) - Update Benefit
* [delete](docs/sdks/benefits/README.md#delete) - Delete Benefit
* [grants](docs/sdks/benefits/README.md#grants) - List Benefit Grants

### [checkout_links](docs/sdks/checkoutlinks/README.md)

* [list](docs/sdks/checkoutlinks/README.md#list) - List Checkout Links
* [create](docs/sdks/checkoutlinks/README.md#create) - Create Checkout Link
* [get](docs/sdks/checkoutlinks/README.md#get) - Get Checkout Link
* [update](docs/sdks/checkoutlinks/README.md#update) - Update Checkout Link
* [delete](docs/sdks/checkoutlinks/README.md#delete) - Delete Checkout Link

### [checkouts](docs/sdks/checkouts/README.md)

* [list](docs/sdks/checkouts/README.md#list) - List Checkout Sessions
* [create](docs/sdks/checkouts/README.md#create) - Create Checkout Session
* [get](docs/sdks/checkouts/README.md#get) - Get Checkout Session
* [client_get](docs/sdks/checkouts/README.md#client_get) - Get Checkout Session from Client

### [custom_fields](docs/sdks/customfields/README.md)

* [list](docs/sdks/customfields/README.md#list) - List Custom Fields
* [create](docs/sdks/customfields/README.md#create) - Create Custom Field
* [get](docs/sdks/customfields/README.md#get) - Get Custom Field
* [update](docs/sdks/customfields/README.md#update) - Update Custom Field
* [delete](docs/sdks/customfields/README.md#delete) - Delete Custom Field

### [customer_meters](docs/sdks/customermeters/README.md)

* [list](docs/sdks/customermeters/README.md#list) - List Customer Meters
* [get](docs/sdks/customermeters/README.md#get) - Get Customer Meter

### [customer_portal_benefit_grants](docs/sdks/customerportalbenefitgrants/README.md)

* [list](docs/sdks/customerportalbenefitgrants/README.md#list) - List Benefit Grants
* [get](docs/sdks/customerportalbenefitgrants/README.md#get) - Get Benefit Grant
* [update](docs/sdks/customerportalbenefitgrants/README.md#update) - Update Benefit Grant

### [customer_portal_customer_meters](docs/sdks/customerportalcustomermeters/README.md)

* [list](docs/sdks/customerportalcustomermeters/README.md#list) - List Meters
* [get](docs/sdks/customerportalcustomermeters/README.md#get) - Get Customer Meter

### [customer_portal_customers](docs/sdks/customerportalcustomers/README.md)

* [get](docs/sdks/customerportalcustomers/README.md#get) - Get Customer
* [update](docs/sdks/customerportalcustomers/README.md#update) - Update Customer
* [get_payment_methods](docs/sdks/customerportalcustomers/README.md#get_payment_methods) - Get Customer Payment Methods
* [add_payment_method](docs/sdks/customerportalcustomers/README.md#add_payment_method) - Add Customer Payment Method
* [delete_payment_method](docs/sdks/customerportalcustomers/README.md#delete_payment_method) - Delete Customer Payment Method

### [customer_portal_downloadables](docs/sdks/customerportaldownloadables/README.md)

* [list](docs/sdks/customerportaldownloadables/README.md#list) - List Downloadables
* [get](docs/sdks/customerportaldownloadables/README.md#get) - Get Downloadable

### [customer_portal_license_keys](docs/sdks/customerportallicensekeys/README.md)

* [list](docs/sdks/customerportallicensekeys/README.md#list) - List License Keys
* [get](docs/sdks/customerportallicensekeys/README.md#get) - Get License Key
* [validate](docs/sdks/customerportallicensekeys/README.md#validate) - Validate License Key
* [activate](docs/sdks/customerportallicensekeys/README.md#activate) - Activate License Key
* [deactivate](docs/sdks/customerportallicensekeys/README.md#deactivate) - Deactivate License Key

### [customer_portal_orders](docs/sdks/customerportalorders/README.md)

* [list](docs/sdks/customerportalorders/README.md#list) - List Orders
* [get](docs/sdks/customerportalorders/README.md#get) - Get Order
* [invoice](docs/sdks/customerportalorders/README.md#invoice) - Get Order Invoice

### [customer_portal_organizations](docs/sdks/customerportalorganizations/README.md)

* [get](docs/sdks/customerportalorganizations/README.md#get) - Get Organization

### [customer_portal_subscriptions](docs/sdks/customerportalsubscriptions/README.md)

* [list](docs/sdks/customerportalsubscriptions/README.md#list) - List Subscriptions
* [get](docs/sdks/customerportalsubscriptions/README.md#get) - Get Subscription
* [update](docs/sdks/customerportalsubscriptions/README.md#update) - Update Subscription
* [cancel](docs/sdks/customerportalsubscriptions/README.md#cancel) - Cancel Subscription

### [customer_sessions](docs/sdks/customersessions/README.md)

* [create](docs/sdks/customersessions/README.md#create) - Create Customer Session

### [customers](docs/sdks/customers/README.md)

* [list](docs/sdks/customers/README.md#list) - List Customers
* [create](docs/sdks/customers/README.md#create) - Create Customer
* [get](docs/sdks/customers/README.md#get) - Get Customer
* [update](docs/sdks/customers/README.md#update) - Update Customer
* [delete](docs/sdks/customers/README.md#delete) - Delete Customer
* [get_external](docs/sdks/customers/README.md#get_external) - Get Customer by External ID
* [update_external](docs/sdks/customers/README.md#update_external) - Update Customer by External ID
* [delete_external](docs/sdks/customers/README.md#delete_external) - Delete Customer by External ID
* [get_state](docs/sdks/customers/README.md#get_state) - Get Customer State
* [get_state_external](docs/sdks/customers/README.md#get_state_external) - Get Customer State by External ID

### [discounts](docs/sdks/discounts/README.md)

* [list](docs/sdks/discounts/README.md#list) - List Discounts
* [create](docs/sdks/discounts/README.md#create) - Create Discount
* [get](docs/sdks/discounts/README.md#get) - Get Discount
* [update](docs/sdks/discounts/README.md#update) - Update Discount
* [delete](docs/sdks/discounts/README.md#delete) - Delete Discount

### [events](docs/sdks/events/README.md)

* [list](docs/sdks/events/README.md#list) - List Events
* [list_names](docs/sdks/events/README.md#list_names) - List Event Names
* [get](docs/sdks/events/README.md#get) - Get Event
* [ingest](docs/sdks/events/README.md#ingest) - Ingest Events

### [files](docs/sdks/files/README.md)

* [list](docs/sdks/files/README.md#list) - List Files
* [create](docs/sdks/files/README.md#create) - Create File
* [uploaded](docs/sdks/files/README.md#uploaded) - Complete File Upload
* [update](docs/sdks/files/README.md#update) - Update File
* [delete](docs/sdks/files/README.md#delete) - Delete File

### [license_keys](docs/sdks/licensekeys/README.md)

* [list](docs/sdks/licensekeys/README.md#list) - List License Keys
* [get](docs/sdks/licensekeys/README.md#get) - Get License Key
* [update](docs/sdks/licensekeys/README.md#update) - Update License Key
* [get_activation](docs/sdks/licensekeys/README.md#get_activation) - Get Activation

### [meters](docs/sdks/meters/README.md)

* [list](docs/sdks/meters/README.md#list) - List Meters
* [create](docs/sdks/meters/README.md#create) - Create Meter
* [get](docs/sdks/meters/README.md#get) - Get Meter
* [update](docs/sdks/meters/README.md#update) - Update Meter
* [quantities](docs/sdks/meters/README.md#quantities) - Get Meter Quantities

### [metrics](docs/sdks/metrics/README.md)

* [get](docs/sdks/metrics/README.md#get) - Get Metrics
* [limits](docs/sdks/metrics/README.md#limits) - Get Metrics Limits

### [oauth2](docs/sdks/oauth2/README.md)

* [authorize](docs/sdks/oauth2/README.md#authorize) - Authorize
* [token](docs/sdks/oauth2/README.md#token) - Request Token
* [revoke](docs/sdks/oauth2/README.md#revoke) - Revoke Token
* [introspect](docs/sdks/oauth2/README.md#introspect) - Introspect Token
* [userinfo](docs/sdks/oauth2/README.md#userinfo) - Get User Info

### [oauth2_clients](docs/sdks/oauth2clients/README.md)

* [list](docs/sdks/oauth2clients/README.md#list) - List Clients
* [create](docs/sdks/oauth2clients/README.md#create) - Create Client
* [get](docs/sdks/oauth2clients/README.md#get) - Get Client
* [update](docs/sdks/oauth2clients/README.md#update) - Update Client
* [delete](docs/sdks/oauth2clients/README.md#delete) - Delete Client

### [orders](docs/sdks/orders/README.md)

* [list](docs/sdks/orders/README.md#list) - List Orders
* [get](docs/sdks/orders/README.md#get) - Get Order
* [invoice](docs/sdks/orders/README.md#invoice) - Get Order Invoice

### [organizations](docs/sdks/organizations/README.md)

* [list](docs/sdks/organizations/README.md#list) - List Organizations
* [create](docs/sdks/organizations/README.md#create) - Create Organization
* [get](docs/sdks/organizations/README.md#get) - Get Organization
* [update](docs/sdks/organizations/README.md#update) - Update Organization


### [products](docs/sdks/products/README.md)

* [list](docs/sdks/products/README.md#list) - List Products
* [create](docs/sdks/products/README.md#create) - Create Product
* [get](docs/sdks/products/README.md#get) - Get Product
* [update](docs/sdks/products/README.md#update) - Update Product
* [update_benefits](docs/sdks/products/README.md#update_benefits) - Update Product Benefits

### [refunds](docs/sdks/refunds/README.md)

* [list](docs/sdks/refunds/README.md#list) - List Refunds
* [create](docs/sdks/refunds/README.md#create) - Create Refund

### [subscriptions](docs/sdks/subscriptions/README.md)

* [list](docs/sdks/subscriptions/README.md#list) - List Subscriptions
* [export](docs/sdks/subscriptions/README.md#export) - Export Subscriptions
* [get](docs/sdks/subscriptions/README.md#get) - Get Subscription
* [update](docs/sdks/subscriptions/README.md#update) - Update Subscription
* [revoke](docs/sdks/subscriptions/README.md#revoke) - Revoke Subscription

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or raise an error.

By default an API error will raise a `Errors::APIError`, which has the following properties:

| Property       | Type                                    | Description           |
|----------------|-----------------------------------------|-----------------------|
| `message`     | *string*                                 | The error message     |
| `status_code`  | *int*                                   | The HTTP status code  |
| `raw_response` | *Faraday::Response*                     | The raw HTTP response |
| `body`        | *string*                                 | The response content  |

When custom error responses are specified for an operation, the SDK may also throw their associated exception. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `list` method throws the following exceptions:

| Error Type                          | Status Code | Content Type     |
| ----------------------------------- | ----------- | ---------------- |
| Models::Errors::HTTPValidationError | 422         | application/json |
| Errors::APIError                    | 4XX, 5XX    | \*/\*            |

### Example

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

begin
    res = s.organizations.list(slug="<value>", page=768_578, limit=547_272, sorting=[
      Models::Shared::OrganizationSortProperty::NAME,
    ])

    if ! res.list_resource_organization.nil?
      # handle response
    end
rescue Models::Errors::HTTPValidationError => e
  # handle $e->$container data
  throw $e;
rescue Errors::APIError => e
  # handle default exception
  raise e
end

```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Name

You can override the default server globally by passing a server name to the `server (Symbol)` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the names associated with the available servers:

| Name         | Server                         | Description            |
| ------------ | ------------------------------ | ---------------------- |
| `production` | `https://api.polar.sh`         | Production environment |
| `sandbox`    | `https://sandbox-api.polar.sh` | Sandbox environment    |

#### Example

```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      server: "sandbox",
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.organizations.list(slug="<value>", page=768_578, limit=547_272, sorting=[
  Models::Shared::OrganizationSortProperty::NAME,
])

if ! res.list_resource_organization.nil?
  # handle response
end

```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `server_url (String)` optional parameter when initializing the SDK client instance. For example:
```ruby
require 'polar_sdk'

s = ::OpenApiSDK::Polar.new(
      server_url: "https://api.polar.sh",
      access_token: "<YOUR_BEARER_TOKEN_HERE>",
    )

res = s.organizations.list(slug="<value>", page=768_578, limit=547_272, sorting=[
  Models::Shared::OrganizationSortProperty::NAME,
])

if ! res.list_resource_organization.nil?
  # handle response
end

```
<!-- End Server Selection [server] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=polar-sdk&utm_campaign=ruby)
