# WebhookCheckoutUpdatedPayload

Sent when a checkout is updated.

**Discord & Slack support:** Basic


## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 | Example                                                     |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `type`                                                      | *::String*                                                  | :heavy_check_mark:                                          | N/A                                                         | checkout.updated                                            |
| `data`                                                      | [Models::Shared::Checkout](../../models/shared/checkout.md) | :heavy_check_mark:                                          | Checkout session data retrieved using an access token.      |                                                             |