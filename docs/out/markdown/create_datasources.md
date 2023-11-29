# Creating RMF data sources {#create_datasources .task}

To access RMF Monitor III metrics in Grafana, you need to connect to the Distributed Data Servers by adding an RMF data source.

-   You must have installed the RMF for z/OS Grafana plugin. See [Installing the RMF for z/OS plugin on Grafana](install_grafana_plugin.md).
-   You must know the hostname and port number of Distributed Data Server.

1.  Go to **Apps** \> **IBM RMF** \> **Add RMF Data Source**.

    Alternatively, you can click **Administration** \> **Data sources** \> **+ Add new data source**, then search for the IBM RMF to choose a data source type.

    **Note:** The navigation of the user interface can differ based on the Grafana version that is currently installed.

2.  Enter a name for the data source in the **Name** field.

3.  Set **Default** ![](images/toggle-off.png) to ON to make the added data source the default one.

    **Note:** When you create new panels, the default data source is preselected.

4.  Enter the details for the following fields in the Server Information section:

    |Fields|Action|
    |------|------|
    |**Server**|Enter the hostname of the DDS in this field.|
    |**Port**|Enter the port number of the DDS in this field.|

5.  Choose one of the following methods to create the data source:

    |Methods|Description|Action|
    |-------|-----------|------|
    |Create the data source with no authentication|You do not require any credentials to create the data source.|Click **Save & test**.The Data source is working message is displayed if the connection to DDS succeeds.

|
    |Create the data source with SSL and Basic Authentication|You must select the **Use SSL** radio button. Optionally you can provide a username and password to create the data source.|    1.  Set **Use SSL** ![](images/toggle-off.png) to ON to enable the secure connection.

**Remember:** When you enable SSL, the **Verify the server’s certificate chain/hostname** option is also enabled.

You can turn OFF the **Verify the server’s certificate chain/hostname** option if you are willing to accept any certificate presented by the DDS and any hostname listed in that certificate. However, this practice is not considered secure and is typically used in development or testing environments.

    2.  **Optional**: Enter the credentials of the DDS in the **Username** and **Password** fields.
    3.  Click **Save & test**.

The Data source is working message is displayed if the connection to DDS succeeds.

|


You have added the RMF data source.

You can refer to the [RMF master dashboard](db_ovw.md) topic for information about RMF master dashboard and its features.

**Previous topic:**[Installing the RMF for z/OS plugin on Grafana](install_grafana_plugin.md)

**Next topic:**[RMF master dashboard](db_ovw.md)

