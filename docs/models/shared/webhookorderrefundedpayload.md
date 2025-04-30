# WebhookOrderRefundedPayload

Sent when an order is fully or partially refunded.

**Discord & Slack support:** Full


## Fields

| Field                                                 | Type                                                  | Required                                              | Description                                           | Example                                               |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `type`                                                | *::String*                                            | :heavy_check_mark:                                    | N/A                                                   | order.refunded                                        |
| `data`                                                | [Models::Shared::Order](../../models/shared/order.md) | :heavy_check_mark:                                    | N/A                                                   |                                                       |