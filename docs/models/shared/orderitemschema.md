# OrderItemSchema

An order line item.


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Creation timestamp of the object.                                    |
| `modified_at`                                                        | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Last modification timestamp of the object.                           |
| `id`                                                                 | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the object.                                                |
| `label`                                                              | *::String*                                                           | :heavy_check_mark:                                                   | Description of the line item charge.                                 |
| `amount`                                                             | *::Integer*                                                          | :heavy_check_mark:                                                   | Amount in cents, before discounts and taxes.                         |
| `tax_amount`                                                         | *::Integer*                                                          | :heavy_check_mark:                                                   | Sales tax amount in cents.                                           |
| `proration`                                                          | *T::Boolean*                                                         | :heavy_check_mark:                                                   | Whether this charge is due to a proration.                           |
| `product_price_id`                                                   | *::String*                                                           | :heavy_check_mark:                                                   | Associated price ID, if any.                                         |