# WebhookCustomerDeletedPayload

Sent when a customer is deleted.

**Discord & Slack support:** Basic


## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 | Example                                                     |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `type`                                                      | *::String*                                                  | :heavy_check_mark:                                          | N/A                                                         | customer.deleted                                            |
| `data`                                                      | [Models::Shared::Customer](../../models/shared/customer.md) | :heavy_check_mark:                                          | A customer in an organization.                              |                                                             |