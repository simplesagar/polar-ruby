# WebhookOrderUpdatedPayload

Sent when an order is updated.

An order is updated when:

* Its status changes, e.g. from `pending` to `paid`.
* It's refunded, partially or fully.

**Discord & Slack support:** Full


## Fields

| Field                                                 | Type                                                  | Required                                              | Description                                           | Example                                               |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `type`                                                | *::String*                                            | :heavy_check_mark:                                    | N/A                                                   | order.updated                                         |
| `data`                                                | [Models::Shared::Order](../../models/shared/order.md) | :heavy_check_mark:                                    | N/A                                                   |                                                       |