# WebhookBenefitGrantRevokedPayload

Sent when a benefit grant is revoked.

**Discord & Slack support:** Basic


## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       | Example                                                                           |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `type`                                                                            | *::String*                                                                        | :heavy_check_mark:                                                                | N/A                                                                               | benefit_grant.revoked                                                             |
| `data`                                                                            | [Models::Shared::BenefitGrantWebhook](../../models/shared/benefitgrantwebhook.md) | :heavy_check_mark:                                                                | N/A                                                                               |                                                                                   |