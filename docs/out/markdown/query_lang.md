# IBM RMF query languages {#query_lang .concept}

In Grafana, queries are essential for fetching and transforming data from RMF data sources.

Executing a query is a process that involves defining the data source, specifying the desired data to retrieve, and applying relevant filters or transformations. IBM RMF for z/OS Grafana plugin provides a user-friendly RMF query editor that maximizes its unique capabilities. Grafana panels retrieve data for visualization from RMF data sources via queries.

You can use the following types of queries to retrieve data from the specified RMF data source:

-   Metric query – Use this query to retrieve RMF Monitor III metrics.
-   Report query – Use this query to retrieve RMF Monitor III reports.

## Metric query syntax {#section_ass_fl3_ryb .section}

The syntax of the Metric query is as follows:

`resource\_type.metric\_description {qualifications}`

Where:

-   `resource\_type` is the type of resource for which information is requested. You must enter the appropriate value in the `resource\_type` field.

    The available resource types are documented in the [z/OS RMF Monitor III resource model](https://www.ibm.com/docs/en/zos/3.1.0?topic=models-zos-rmf-monitor-iii-resource-model#zosm3) topic in the *z/OS Resource Measurement Facility Programmer's Guide*.

-   `metric\_description` is the name of the metric for the selected resource type.

    After entering the resource type, you can choose the metric description from the drop-down list.

-   `qualifications` is an optional parameter and can contain any or all the following attributes separated by a comma:
    -   `ulq`: The name of the resource type at the upper level.
    -   `name`: The name of the resource.
    -   `filter`: The filter helps to focus on the data of your interest when requesting a list of values.

        You can use one of the following values for the `filter` attribute:

        PAT=< pattern\>
        :   Specifies one or more patterns that must match the name part of a list element.

        LB=<number\>
        :   Specifies a lower bound value. Only list elements with values higher than the given lower bound are returned.

        UB=<number\>
        :   Specifies an upper bound value. Only list elements with values lower than the established upper bound are returned.

        HI=<integer\>
        :   Only the highest <integer\> list elements are returned \(mutually exclusive with LO\).

        LO=<integer\>
        :   Only the lowest <integer\> list elements are returned \(mutually exclusive with HI\).

        ORD=< NA \| ND \| VA \| VD \| NN\>
        :   -   NA - Sort the list of names by their names in ascending order.
-   ND – Sort the list of names by their names in descending order.
-   VA – Sort the list of values by their values in ascending order.
-   VD – Sort the list of values by their values in descending order.
-   NN - If you do not want to have any order, you can specify ORD=NN.
    -   `workscope`: To qualify a request for performance data in more detail about address spaces and WLM entities. You can use one of the following values for the workscope attribute:
        -   G - Global \(no workscope required\)
        -   W - WLM workload
        -   S - WLM service class
        -   P - WLM service class period
        -   R - WLM report class
        -   J - Job

**Examples**:

``` {#codeblock_pfq_1bv_ryb}
SYSPLEX.% total physical utilization \(AAP\) by partition
```

``` {#codeblock_bs5_r3j_lzb}
COUPLING\_FACILITY.% processor utilization
```

``` {#codeblock_pht_x3j_lzb}
CPC.% total physical utilization \(shared IIP\)
```

``` {#codeblock_f4k_cbv_ryb}
MVS\_IMAGE.% delay by WLM report class period {name=RS21}
```

``` {#codeblock_qqh_mbv_ryb}
MVS\_IMAGE.% workflow by WLM report class period {ulq=RS21,name=RS2\*,filter=ORD=NA,workscope=,,G}
```

## Report query syntax {#section_l5k_fm3_ryb .section}

The syntax of the Report query is as follows:

`resource\_type.REPORT.report\_name`

Where:

-   `resource\_type` is the type of resource for which information is requested. You must enter the appropriate value in the `resource\_type` field.
-   `report\_name` is the name of the report.

    You can find the report names in the [Interactive performance analysis with Monitor III](https://www.ibm.com/docs/en/zos/3.1.0?topic=analysis-interactive-performance-monitor-iii), which is documented in the *z/OS Resource Measurement Facility Report Analysis*.

    **Note:** You can view reports on the Grafana dashboard only for the resource types `SYSPLEX` and `MVS_IMAGE`.


**Examples**:

``` {#codeblock_int_pbv_ryb}
SYSPLEX.REPORT.CACHSUM
```

``` {#codeblock_l5g_rbv_ryb}
SYSPLEX.REPORT.CPC
```

**Previous topic:**[Applying visualization to RMF data](apply_visualize.md)

**Next topic:**[RMF Variable Query syntax](variables.md)

