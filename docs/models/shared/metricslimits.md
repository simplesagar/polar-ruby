# MetricsLimits

Date limits to get metrics.


## Fields

| Field                                                                                   | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `min_date`                                                                              | [DateTime](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/DateTime.html)            | :heavy_check_mark:                                                                      | Minimum date to get metrics.                                                            |
| `intervals`                                                                             | [Models::Shared::MetricsIntervalsLimits](../../models/shared/metricsintervalslimits.md) | :heavy_check_mark:                                                                      | Date interval limits to get metrics for each interval.                                  |