# WebhookRefundCreatedPayload

Sent when a refund is created regardless of status.

**Discord & Slack support:** Full


## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             | Example                                                 |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `type`                                                  | *::String*                                              | :heavy_check_mark:                                      | N/A                                                     | refund.created                                          |
| `data`                                                  | [Models::Shared::Refund](../../models/shared/refund.md) | :heavy_check_mark:                                      | N/A                                                     |                                                         |