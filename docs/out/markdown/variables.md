# RMF Variable Query syntax {#variables .concept}

Variables are a powerful tool to create more interactive and dynamic dashboards. They offer a way to replace hard-coded values in metric queries and panel titles with placeholders for values.

Variables make it easy to change the data displayed in your dashboard simply by selecting a value from the drop-down list at the top. Using variables in your dashboard simplifies maintenance, particularly if you have multiple identical data sources. Instead of creating separate dashboards for each data source, you can create one dashboard and use variables to change what you are viewing.

**Important:** It's important to note that variables don't have a default value. Each variable drop-down list in Dashboard settings displays the variable list in the order it appears.

You can define a dashboard variable in **Dashboard Settings** \> **Variables** using Grafana's RMF Variable Query syntax with and without a filter.

## Syntax of the query without a filter {#section_ttx_pjc_fzb .section}

The general syntax of the query without a filter is as follows:

`SELECT <COLUMN_NAME> FROM RESOURCE WHERE condition1 or condition2 or condition3`

**Note:** The `<COLUMN_NAME>` is limited to “label” and `RESOURCE` is limited to “resource” only and cannot be used for other purposes.

Where:

-   `condition1`: ULQ=Value and TYPE=Value
-   `condition2`: Name=Value and TYPE=Value
-   `condition3`: Name=Value and ULQ=Value and TYPE=Value

**Examples for condition1:**

-   `select label from resource where ulq="hostname of the DDS" and type="CHANNEL\_PATH"`
-   `select label from resource where ulq="hostname of the DDS" and type="ALL\_CHANNELS"`

**Examples for condition2:**

`select label from resource where name="resource\_name" and type="SYSPLEX"`

**Examples for condition3:**

-   `select label from resource where ulq="hostname of the DDS" and name="\*" and type="CHANNEL\_PATH"`
-   `select label from resource where ulq="hostname of the DDS" and name="\*" and type="ALL\_CHANNELS"`

## Syntax of the query with a filter {#section_wh3_dkc_fzb .section}

The general syntax of the RMF query with a filter is as follows:

`SELECT <COLUMN_NAME> FROM RESOURCE WHERE condition`

Where `condition` is Name=Value and ULQ=Value and TYPE=Value and Filter= Value

**Examples for condition:**

`select label from resource where name="resource\_name" and type="SYSPLEX" and filter="MVS\_IMAGE"`

To learn how to effectively add and manage variables of your choice in Grafana, you can refer to the [Grafana](https://grafana.com/docs/grafana/latest/dashboards/variables/add-template-variables/) documentation.

**Previous topic:**[IBM RMF query languages](query_lang.md)

**Next topic:**[Introduction to Alerts](alerts.md)

