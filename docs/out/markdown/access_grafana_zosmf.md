# Accessing the Grafana dashboard {#access_grafana_zosmf .task}

You can access the Grafana dashboard from the Resource Monitoring page of z/OSMF to investigate the RMF Monitor III metrics and reports.

You must have completed the following tasks:

-   Defined the Grafana server in z/OSMF. See [Defining the Grafana server](define_grafana_zosmf.md).
-   Created a user in the Grafana Server with an appropriate role using the TSO user ID. For more information, refer to the [Grafana](https://grafana.com/docs/grafana/latest/administration/user-management/) documentation.

1.  Enter the URL of z/OSMF in a web browser.

2.  Log in to z/OSMF if you are not already logged in.

3.  Double-click **Resource Monitoring**.

4.  Select the Grafana server that you want to access from the drop-down list.

5.  Click **Load Grafana**.


You have accessed Grafana from z/OSMF.

You can perform the following tasks:

-   Sign in to the Grafana server if you are not already signed in.
-   Add a RMF data source to fetch data from Distributed Data Servers \(DDS\). See [Creating RMF data sources](Creating RMF data sourcesabout:blankcreate_datasources.dita).

**Parent topic:**[Grafana through IBM z/OS Management Facility](grafana_via_zosmf.md)

**Previous topic:**[Defining the Grafana server](define_grafana_zosmf.md)

