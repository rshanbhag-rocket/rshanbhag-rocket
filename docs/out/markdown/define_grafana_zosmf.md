# Defining the Grafana server {#define_grafana_zosmf .task}

You must define the Grafana server as a target system in z/OSMF to access Grafana from the Resource Monitoring page of z/OSMF.

You must have completed the following tasks:

-   Installed and configured z/OSMF. For more information, refer to [*z/OS Management Facility Configuration Guide*.](https://www.ibm.com/docs/en/zos/3.1.0?topic=facility-zos-management-configuration-guide)
-   Installed Grafana v9.5.1 or later. For more information, refer to [Grafana](https://grafana.com/docs/grafana/latest/setup-grafana/installation/) documentation.
-   Installed the IBM RMF for z/OS Grafana plugin. See [Installing the RMF for z/OS plugin on Grafana](install_grafana_plugin.md).

1.  Enter the URL of z/OSMF in a web browser.

2.  Log in to z/OSMF if you are not already logged in.

3.  Double-click **System Status**.

4.  Click **Add Entry** from the **Actions** drop-down list.

5.  Perform the following steps to add details about the Grafana server:

    1.  Enter a name for the Grafana server in the **Resource name** field.

        The **Resource name** is the required field, and you must provide a unique name. The **Resource name** can contain up to 24 characters including alphanumeric characters \(A-Z, a-z, and 0-9\) and special characters \(@ \# $\).

        **Note:** You must note that the **Resource name** is not case sensitive. Therefore, the entries with similar names but different capitalization, such as SYS1 and Sys1 are considered as identical by the system.

    2.  Enter the host name or IP address of the Grafana server that you want to access in the **Host name or IP address** field.

        The host name or IP address can contain up to 4000 characters.

    3.  Select **Grafana** from the **Target system type** drop-down list.

    4.  Select the **Use HTTPS** checkbox to enable secure communication.

    5.  Enter the port number where the Grafana server is hosted in the **Port** field.

        The **Port** is the required field, and the default port number is set to 3000.

        **Tip:** Alternatively, you can use **up-down** controls to specify the port number.

6.  Click **OK**.


You have defined the Grafana server as the target system. The connectivity status of the specified Grafana server is displayed as **Connected** on the System Status page if successful.

You can perform the following tasks:

-   Modify or Remove the Grafana server by clicking the **Action** drop-down menu from the System Statuss page.
-   Access Grafana dashboards. See [Accessing the Grafana dashboard](access_grafana_zosmf.md).

**Parent topic:**[Grafana through IBM z/OS Management Facility](grafana_via_zosmf.md)

**Previous topic:**[Grafana through IBM z/OS Management Facility](grafana_via_zosmf.md)

**Next topic:**[Accessing the Grafana dashboard](access_grafana_zosmf.md)

