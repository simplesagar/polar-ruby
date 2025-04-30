# WebhookSubscriptionCanceledPayload

Sent when a subscription is canceled.
Customers might still have access until the end of the current period.

**Discord & Slack support:** Full


## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `type`                                                              | *::String*                                                          | :heavy_check_mark:                                                  | N/A                                                                 | subscription.canceled                                               |
| `data`                                                              | [Models::Shared::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                  | N/A                                                                 |                                                                     |