:original_name: vpcep_02_0302.html

.. _vpcep_02_0302:

Step 1: Create a VPC Endpoint for Connecting to DNS
===================================================

Scenarios
---------

This section describes how to create a VPC endpoint for accessing a DNS server, in order to forward requests of resolving OBS domain names.

Prerequisites
-------------

The required VPC endpoint service is available.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.
#. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. On the **VPC Endpoints** page, click **Create VPC Endpoint**.

   The **Create VPC Endpoint** page is displayed.


   .. figure:: /_static/images/en-us_image_0000002185000233.png
      :alt: **Figure 1** Create VPC Endpoint

      **Figure 1** Create VPC Endpoint

5. Configure VPC endpoint parameters.

   .. _vpcep_02_0302__table85139343530:

   .. table:: **Table 1** VPC endpoint parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                          |
      +===================================+======================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is to be deployed.                                                                                       |
      |                                   |                                                                                                                                                      |
      |                                   | Resources in different regions cannot communicate with each other over an intranet. For lower latency and quicker access, select the nearest region. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | There are two options:                                                                                                                               |
      |                                   |                                                                                                                                                      |
      |                                   | -  **Cloud service**: Select this option if the VPC endpoint service to be accessed is a cloud service.                                              |
      |                                   | -  **Find a service by name**: Select this option if the VPC endpoint service to be accessed is a private service of your own.                       |
      |                                   |                                                                                                                                                      |
      |                                   | In this example, select **Cloud service**.                                                                                                           |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service List                      | This parameter is available only when you select **Cloud service** for **Service Category**.                                                         |
      |                                   |                                                                                                                                                      |
      |                                   | The VPC endpoint service has been created by the O&M personnel and you can directly use it.                                                          |
      |                                   |                                                                                                                                                      |
      |                                   | In this example, select **com.t-systems.otc.eu-de.dns**.                                                                                             |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Create a Private Domain Name      | If you want to access a VPC endpoint using a domain name, select **Create a Private Domain Name**.                                                   |
      |                                   |                                                                                                                                                      |
      |                                   | This parameter is only available for interface VPC endpoints.                                                                                        |
      |                                   |                                                                                                                                                      |
      |                                   | -  For the gateway type, this parameter is unavailable.                                                                                              |
      |                                   | -  For the interface type, this parameter is optional.                                                                                               |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is to be deployed.                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                 |
      |                                   |                                                                                                                                                      |
      |                                   | Specifies the subnet where the VPC endpoint is to be deployed.                                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | IPv4 Address                      | This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                 |
      |                                   |                                                                                                                                                      |
      |                                   | Specifies the IPv4 address of the VPC endpoint.                                                                                                      |
      |                                   |                                                                                                                                                      |
      |                                   | You can select **Automatically assign** or **Manually specify**.                                                                                     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Access Control                    | This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                 |
      |                                   |                                                                                                                                                      |
      |                                   | It controls IP addresses and CIDR blocks that are allowed to access the VPC endpoint.                                                                |
      |                                   |                                                                                                                                                      |
      |                                   | -  If **Access Control** is enabled, only IP addresses or CIDR blocks in the whitelist are allowed to access the VPC endpoint.                       |
      |                                   | -  If **Access Control** is disabled, any IP address or CIDR block can access the VPC endpoint.                                                      |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Whitelist                         | This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service and enable access control.       |
      |                                   |                                                                                                                                                      |
      |                                   | Lists the IP addresses or CIDR blocks that are allowed to access the VPC endpoint. You can add a maximum of 20 records.                              |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                          |
      |                                   |                                                                                                                                                      |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add up to 20 tags to each VPC endpoint.                                 |
      |                                   |                                                                                                                                                      |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <vpcep_02_0302__table775312110110>`.                                              |
      |                                   |                                                                                                                                                      |
      |                                   | .. note::                                                                                                                                            |
      |                                   |                                                                                                                                                      |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                         |
      |                                   |                                                                                                                                                      |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Provides supplementary information about the VPC endpoint.                                                                                           |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_02_0302__table775312110110:

   .. table:: **Table 2** Tag requirements for VPC endpoints

      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                                          |
      +===================================+======================================================================================+
      | Tag key                           | -  Cannot be left blank.                                                             |
      |                                   | -  Must be unique for each resource.                                                 |
      |                                   | -  Can contain a maximum of 36 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Tag value                         | -  Can contain a maximum of 43 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+

6. .. _vpcep_02_0302__li20290450181218:

   Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page, modify the parameters as needed, and click **Submit**.

7. Click **Back to VPC Endpoint List** after the task is submitted.

   If the status of the VPC endpoint changes to **Accepted**, the VPC endpoint for connecting to **com.t-systems.otc.eu-de.dns** is created.

8. In the VPC endpoint list, click the ID of the VPC endpoint to view its details.

   After a VPC endpoint for accessing interface VPC endpoint services is created, a private IP address is assigned together with a private domain name if you select **Create a Private Domain Name** during creation.


   .. figure:: /_static/images/en-us_image_0000002184964665.png
      :alt: **Figure 2** Summary of the VPC endpoint

      **Figure 2** Summary of the VPC endpoint

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
