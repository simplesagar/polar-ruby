# WebhookSubscriptionRevokedPayload

Sent when a subscription is revoked, the user looses access immediately.
Happens when the subscription is canceled, or payment is past due.

**Discord & Slack support:** Full


## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `type`                                                              | *::String*                                                          | :heavy_check_mark:                                                  | N/A                                                                 | subscription.revoked                                                |
| `data`                                                              | [Models::Shared::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                  | N/A                                                                 |                                                                     |