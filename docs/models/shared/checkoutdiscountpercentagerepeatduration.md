# CheckoutDiscountPercentageRepeatDuration

Schema for a percentage discount that is applied on every invoice
for a certain number of months.


## Fields

| Field                                                                       | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `duration`                                                                  | [Models::Shared::DiscountDuration](../../models/shared/discountduration.md) | :heavy_check_mark:                                                          | N/A                                                                         |
| `duration_in_months`                                                        | *::Integer*                                                                 | :heavy_check_mark:                                                          | N/A                                                                         |
| `type`                                                                      | [Models::Shared::DiscountType](../../models/shared/discounttype.md)         | :heavy_check_mark:                                                          | N/A                                                                         |
| `basis_points`                                                              | *::Integer*                                                                 | :heavy_check_mark:                                                          | N/A                                                                         |
| `id`                                                                        | *::String*                                                                  | :heavy_check_mark:                                                          | The ID of the object.                                                       |
| `name`                                                                      | *::String*                                                                  | :heavy_check_mark:                                                          | N/A                                                                         |
| `code`                                                                      | *::String*                                                                  | :heavy_check_mark:                                                          | N/A                                                                         |