# WebhookProductUpdatedPayload

Sent when a product is updated.

**Discord & Slack support:** Basic


## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               | Example                                                   |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `type`                                                    | *::String*                                                | :heavy_check_mark:                                        | N/A                                                       | product.updated                                           |
| `data`                                                    | [Models::Shared::Product](../../models/shared/product.md) | :heavy_check_mark:                                        | A product.                                                |                                                           |