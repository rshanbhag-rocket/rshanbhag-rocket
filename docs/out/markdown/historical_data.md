# Historical data collection {#historical_data .reference}

In Grafana, you can collect historical data using absolute and relative time ranges.

Collecting historical data is a common practice across organizations for various purposes. The importance and use of historical data are significant in decision-making, research, analysis, and planning. Analyzing historical data provides valuable insights into the status, usage, performance, and health of various resources.

You can also access cached metric data for queries, data sources, and timestamp combinations that have already viewed by other user on Grafana. This means that if any user requests metrics data for the same query, datasource, and timestamp, the cached data can be displayed faster than a service call from DDS. If data for a particular timestamp is not found in the cache, it will be fetched by a service call from DDS. This feature can save you time and provide a faster experience accessing metric data.

The following example shows the percentage of time during the report interval that the system job or enclave was waiting for a processor by specifying absolute time:



Similarly, you can collect the data for the percentage of time delay for a processor by specifying the relative time range:



**Previous topic:**[Introduction to Alerts](alerts.md)

**Next topic:**[Error reporting in the plugin](error_reports.md)

