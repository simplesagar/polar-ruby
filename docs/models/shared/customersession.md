# CustomerSession

A customer session that can be used to authenticate as a customer.


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Creation timestamp of the object.                                    |
| `modified_at`                                                        | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Last modification timestamp of the object.                           |
| `id`                                                                 | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the object.                                                |
| `token`                                                              | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  |
| `expires_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | N/A                                                                  |
| `customer_portal_url`                                                | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  |
| `customer_id`                                                        | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  |
| `customer`                                                           | [Models::Shared::Customer](../../models/shared/customer.md)          | :heavy_check_mark:                                                   | A customer in an organization.                                       |