# WebhookCheckoutCreatedPayload

Sent when a new checkout is created.

**Discord & Slack support:** Basic


## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 | Example                                                     |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `type`                                                      | *::String*                                                  | :heavy_check_mark:                                          | N/A                                                         | checkout.created                                            |
| `data`                                                      | [Models::Shared::Checkout](../../models/shared/checkout.md) | :heavy_check_mark:                                          | Checkout session data retrieved using an access token.      |                                                             |