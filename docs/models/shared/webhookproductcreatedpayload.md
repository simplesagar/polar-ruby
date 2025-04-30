# WebhookProductCreatedPayload

Sent when a new product is created.

**Discord & Slack support:** Basic


## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               | Example                                                   |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `type`                                                    | *::String*                                                | :heavy_check_mark:                                        | N/A                                                       | product.created                                           |
| `data`                                                    | [Models::Shared::Product](../../models/shared/product.md) | :heavy_check_mark:                                        | A product.                                                |                                                           |