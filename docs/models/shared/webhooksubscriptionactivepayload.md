# WebhookSubscriptionActivePayload

Sent when a subscription becomes active,
whether because it's a new paid subscription or because payment was recovered.

**Discord & Slack support:** Full


## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `type`                                                              | *::String*                                                          | :heavy_check_mark:                                                  | N/A                                                                 | subscription.active                                                 |
| `data`                                                              | [Models::Shared::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                  | N/A                                                                 |                                                                     |