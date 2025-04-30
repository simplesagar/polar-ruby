# WebhookCustomerCreatedPayload

Sent when a new customer is created.

A customer can be created:

* After a successful checkout.
* Programmatically via the API.

**Discord & Slack support:** Basic


## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 | Example                                                     |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `type`                                                      | *::String*                                                  | :heavy_check_mark:                                          | N/A                                                         | customer.created                                            |
| `data`                                                      | [Models::Shared::Customer](../../models/shared/customer.md) | :heavy_check_mark:                                          | A customer in an organization.                              |                                                             |