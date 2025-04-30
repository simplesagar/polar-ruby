# ProductPriceCustomCreate

Schema to create a pay-what-you-want price.


## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `amount_type`                                     | *::String*                                        | :heavy_check_mark:                                | N/A                                               |
| `price_currency`                                  | *T.nilable(::String)*                             | :heavy_minus_sign:                                | The currency. Currently, only `usd` is supported. |
| `minimum_amount`                                  | *T.nilable(::Integer)*                            | :heavy_minus_sign:                                | The minimum amount the customer can pay.          |
| `maximum_amount`                                  | *T.nilable(::Integer)*                            | :heavy_minus_sign:                                | The maximum amount the customer can pay.          |
| `preset_amount`                                   | *T.nilable(::Integer)*                            | :heavy_minus_sign:                                | The initial amount shown to the customer.         |