# EventName


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `name`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | The name of the event.                                               |
| `source`                                                             | [Models::Shared::EventSource](../../models/shared/eventsource.md)    | :heavy_check_mark:                                                   | N/A                                                                  |
| `occurrences`                                                        | *::Integer*                                                          | :heavy_check_mark:                                                   | Number of times the event has occurred.                              |
| `first_seen`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | The first time the event occurred.                                   |
| `last_seen`                                                          | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | The last time the event occurred.                                    |