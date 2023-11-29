# Applying visualization to RMF data {#apply_visualize .task}

By adding panels to dashboards, you can effectively present your RMF data in a visual format. Each panel must require at least one query to display a significant visualization.

You must have completed the following tasks:

-   Installed the IBM RMF for z/OS Grafana plugin. See [Installing the RMF for z/OS plugin on Grafana](install_grafana_plugin.md).
-   Added a RMF data source in Grafana. See [Creating RMF data sources](create_datasources.md).
-   Understood query languages of the RMF. See [IBM RMF query languages](query_lang.md).

1.  Identify the dashboard for which you want to add visualization.

2.  Perform one of the steps described in the following table:

    |Step description|Step \#|
    |----------------|-------|
    |If there are no panels added to the dashboard|Perform step [3](#step_vdz_4fr_ryb).|
    |If at least one panel is added to the dashboard|Perform step [5](#step_qrg_zfr_ryb).|

3.  Click **+ Add visualization** to add visualization to your data.

    **Note:** The navigation of the user interface can differ based on the Grafana version that is currently installed.

    The Edit panel is displayed.

4.  Go to step [6](#step_fvt_l3r_ryb).

5.  Click **Add** \> **Visualization** from the dashboard header.

    ![](images/add_visulize.png)

    The Edit panel is displayed.

6.  Enter a name for the panel in the **Title** field.

    Optionally you can also provide a description for the panel that you are creating.

    When you add the description for the panel, a notification icon ![](images/notification_icon.png) is displayed after the Panel title, as shown in the following image:

    ![](images/notification_display.png)

7.  Select one of the visualization types from the drop-down menu:

    ![](images/visualize_drop-down.png)

    You can choose **Report for IBM RMF for z/OS** or built-in **Bar chart** Grafana visualization types from the drop-down list.

8.  Click the **Query** tab, and then enter a query in the query language of the RMF data source.

    **Note:** You can click **+ Query** to add multiple queries.

9.  Click the **Transformation** tab, and then select a transformation from the list.

    Upon accessing the transformation options, a dedicated row is presented for configuration.

    **Note:** You can click **+ Add Transformation** to add multiple transformations to data.

10. Select the existing data sources from the **Data source** drop-down list.

11. Click the **Time Picker** drop-down list to select relative time range options and set custom absolute time ranges.

    ![](images/time_picker.png)

12. Click the **Refresh dashboard** ![](images/refresh.png) icon to query the RMF data source.

    Grafana provides you with a preview of your query results along with the corresponding visualization.

13. Click **Apply** to view your changes applied to the dashboard.

14. Click **Save**, and then enter a note describing the changes you have made.

15. Click **Save** to store the changes made to the dashboard.


You have applied visualization to the RMF data.

Grafana provides a range of visualizations that cater to different use cases. For more information about the built-in panels, options, and typical usage, refer to the [Grafana](https://grafana.com/docs/grafana/latest/panels-visualizations/visualizations/) documentation.

You can also configure the panel options based on your requirements. For more information refer to the [Grafana](https://grafana.com/docs/grafana/latest/panels-visualizations/configure-panel-options/#edit-a-panel) documentation.

You can add multiple transformation to your data. When there are multiple transformations, Grafana applies them sequentially. Each transformation produces a result set that is passed on to the next transformation in the pipeline. Grafana provides several ways that you can transform data. For entire list of transformations, refer to the [Grafana](https://grafana.com/docs/grafana/latest/panels-visualizations/query-transform-data/transform-data/#transformation-functions) documentation.

**Previous topic:**[RMF master dashboard](db_ovw.md)

**Next topic:**[IBM RMF query languages](query_lang.md)

