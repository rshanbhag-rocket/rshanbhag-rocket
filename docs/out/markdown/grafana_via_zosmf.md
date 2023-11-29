# Grafana through IBM z/OS Management Facility {#grafana_via_zosmf .concept}

When you use IBM® z/OS Management Facility to monitor the performance of the z/OS sysplexes in your environment, you can also access Grafana dashboards from z/OSMF.

You must complete specific tasks to access Grafana through z/OSMF. The following table lists the task flows to access Grafana from z/OSMF:

|Tasks|More information|
|-----|----------------|
|Install and configure z/OSMF.|[*z/OS Management Facility Configuration Guide*](https://www.ibm.com/docs/en/zos/3.1.0?topic=facility-zos-management-configuration-guide)|
|Install Grafana v9.5.1 or later.|[Grafana documentation](https://grafana.com/docs/grafana/latest/setup-grafana/installation/)|
|Configure the z/OSMF server to build and use JSON Web Token \(JWT\).|[Enabling JSON Web Token support](https://www.ibm.com/docs/en/zos/latest?topic=configurations-enabling-json-web-token-support)|
|Configure Grafana to allow JWT.|[Configure JWT authentication](https://grafana.com/docs/grafana/latest/setup-grafana/configure-security/configure-authentication/jwt/)|
|Install the RMF for z/OS plugin on Grafana.|[Installing the RMF for z/OS plugin on Grafana](install_grafana_plugin.md)|
|Define Grafana servers as target systems.|[Defining the Grafana server](define_grafana_zosmf.md)|
|Access Grafana dashboards|[Accessing the Grafana dashboard](access_grafana_zosmf.md)|

1.  [Defining the Grafana server](define_grafana_zosmf.md)  
You must define the Grafana server as a target system in z/OSMF to access Grafana from the Resource Monitoring page of z/OSMF.
2.  [Accessing the Grafana dashboard](access_grafana_zosmf.md)  
You can access the Grafana dashboard from the Resource Monitoring page of z/OSMF to investigate the RMF Monitor III metrics and reports.

**Previous topic:**[Error reporting in the plugin](error_reports.md)

**Next topic:**[Defining the Grafana server](define_grafana_zosmf.md)

