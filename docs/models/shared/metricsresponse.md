# MetricsResponse

Metrics response schema.


## Fields

| Field                                                                         | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `periods`                                                                     | T::Array<[Models::Shared::MetricPeriod](../../models/shared/metricperiod.md)> | :heavy_check_mark:                                                            | List of data for each timestamp.                                              |
| `metrics`                                                                     | [Models::Shared::Metrics](../../models/shared/metrics.md)                     | :heavy_check_mark:                                                            | N/A                                                                           |