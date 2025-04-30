# ProductPriceFixedCreate

Schema to create a fixed price.


## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `amount_type`                                     | *::String*                                        | :heavy_check_mark:                                | N/A                                               |
| `price_amount`                                    | *::Integer*                                       | :heavy_check_mark:                                | The price in cents.                               |
| `price_currency`                                  | *T.nilable(::String)*                             | :heavy_minus_sign:                                | The currency. Currently, only `usd` is supported. |