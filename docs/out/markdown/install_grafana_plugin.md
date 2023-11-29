# Installing the RMF for z/OS plugin on Grafana {#install_grafana_plugin .task}

You must install the IBM® RMF for z/OS Grafana plugin to analyze and visualize RMF Monitor III metrics and reports.

You must have completed the following tasks:

-   Installed RMF for z/OS 3.1 DDS.
-   Installed Grafana 9.5.1 or later.

You must be familiar working with Grafana.

1.  To enable the RMF unsigned plugin to be loaded in Grafana you must perform one of the following sub-steps:

    1.  Set the environment variable GF\_PLUGINS\_ALLOW\_LOADING\_UNSIGNED\_PLUGINS to ibm-rmf,ibm-rmf-datasource,ibm-rmf-report.

    2.  Set the value of **allow\_loading\_unsigned\_plugins** to ibm-rmf,ibm-rmf-datasource,ibm-rmf-report in the \[plugins\] section of the defaults.ini file.

2.  Installing the RMF for z/OS plugin in the Grafana stand-alone application:
3.  Run the following command to install the plugin by using Grafana CLI:

    ``` {#codeblock_frs_byj_lzb}
    grafana cli --pluginUrl https://github.com/IBM/RMF/releases/download/ibm-rmf-grafana/v<version\>/ibm-rmf-grafana-<version\>.zip plugins install ibm-rmf
    ```

    **Remember:** You must replace the value of <version\> for the pluginURL option to version number of the plugin to be installed.

4.  Restart Grafana.

5.  Installing the RMF for z/OS plugin along with Grafana within the Docker environment:
6.  Run the following command to create a volume for storing the Grafana state:

    ``` {#codeblock_w1x_pyj_lzb}
    docker volume create rmf-grafana-data
    ```

7.  Run the following command to create and run a container:

    ``` {#codeblock_v2k_5yj_lzb}
    docker run --name rmf-grafana --hostname rmf-grafana --detach --restart unless-stopped --volume rmf-grafana-data:/var/lib/grafana --publish 3000:3000 --env “GF\_INSTALL\_PLUGINS=https://github.com/IBM/RMF/releases/download/ibm-rmf-grafana/v<version\>/ibm-rmf-grafana-<version\>.zip;ibm-rmf” --env “GF\_PLUGINS\_ALLOW\_LOADING\_UNSIGNED\_PLUGINS=ibm-rmf,ibm-rmf-datasource,ibm-rmf-report” <image>
    ```

    **Remember:** You must replace the values of the following options in the command:

    -   <version\> for the env option to the version number of the plugin to be installed.
    -   <image\> to the version of the Grafana image to be used.
    **Note:** zCX/zLinux images are available at [Container Images for IBM Z and LinuxONE](https://ibm.github.io/ibm-z-oss-hub/main/main.html). Similarly, images of other required platforms are available at [Docker Hub](https://hub.docker.com/).

8.  Enabling the RMF for z/OS plugin on Grafan UI:
9.  Enter the URL of Grafana in your web browser.

10. Enter the username and password of Grafana on the sign-in page.

11. Go to **Administration** \> **Plugins**.

    **Note:** The navigation of the user interface can differ based on the Grafana version that is currently installed.

12. Enter RMF in the **Search** bar on the Plugins page.

13. Click **IBM RMF** in the search results.

14. Click **Enable**.

    **Note:** After you install the IBM RMF for z/OS Grafana plugin, when you open IBM RMF on the Plugins page of Grafana UI, an Invalid plugin signature warning message is displayed.

15. **Optional**: The IBM RMF for z/OS Grafana plugin is signed with the GPG key. You can verify the signature by performing the following steps:
16. Download the PUBLIC\_KEY.asc \(GPG public key\) file.

    The location of the file is as follows:

    [https://github.com/IBM/RMF/blob/main/grafana/rmf-app/PUBLIC\_KEY.asc](https://github.com/IBM/RMF/blob/main/grafana/rmf-app/PUBLIC_KEY.asc)

17. Follow the instructions in the [Importing a public key](https://www.gnupg.org/gph/en/manual.html#AEN84) section of the GPG user guide.

18. Download the IBM RMF for z/OS Grafana plugin \(ibm-rmf-grafana-x.y.z.zip\) and signature file \(ibm-rmf-grafana-x.y.z.zip.asc\) from [https://github.com/IBM/RMF/releases](https://github.com/IBM/RMF/releases).

19. Run the following command to verify the signature:

    ``` {#codeblock_mch_3h5_lzb}
    gpg --verify ibm-rmf-grafana-x.y.z.zip.asc ibm-rmf-grafana-x.y.z.zip
    ```

    Where `x.y.z` is the version number of the IBM RMF for z/OS Grafana plugin.

    For more information, refer to the [GPG](https://www.gnupg.org/gph/en/manual.html#AEN161) user guide.


You have installed the IBM RMF for z/OS Grafana plugin. You can find the **IBM RMF** plugin listed under the **Apps** section.

![](images/app_section.png)

You can add an RMF data source to fetch data from Distributed Data Servers \(DDS\). See [Creating RMF data sources](create_datasources.md).

**Previous topic:**[Release notes](rn.md)

**Next topic:**[Creating RMF data sources](create_datasources.md)

**Related information**  


[Grafana CLI documentation](https://grafana.com/docs/grafana/latest/cli/)

[docker run command](https://docs.docker.com/engine/reference/commandline/run/)

[docker volume create command](https://docs.docker.com/engine/reference/commandline/volume_create/)

