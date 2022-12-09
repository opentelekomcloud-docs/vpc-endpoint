:original_name: en-us_topic_0131645189.html

.. _en-us_topic_0131645189:

Creating a VPC Endpoint
=======================

Scenarios
---------

VPC endpoints are secure and private channels for connecting VPCs to VPC endpoint services.

You can create a VPC endpoint to connect a resource in your VPC to a VPC endpoint service in another VPC of the same region.

A VPC endpoint comes with a VPC endpoint service. VPC endpoints vary depending on the type of the VPC endpoint services that they can access:

-  VPC endpoints for accessing interface VPC endpoint services are elastic network interfaces that have private IP addresses.
-  VPC endpoints for accessing gateway VPC endpoint services are gateways, with routes configured to distribute traffic to the associated VPC endpoint services.

You can create different types of VPC endpoints based the types of associated VPC endpoint services:

-  :ref:`Creating a VPC Endpoint for Accessing Interface VPC Endpoint Services <en-us_topic_0131645189__section339372615535>`
-  :ref:`Creating a VPC Endpoint for Accessing Gateway VPC Endpoint Services <en-us_topic_0131645189__section3281125041216>`

.. _en-us_topic_0131645189__section339372615535:

Creating a VPC Endpoint for Accessing Interface VPC Endpoint Services
---------------------------------------------------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the required region and project.

#. Choose **Service List** > **Networking** > **VPC Endpoint**.

#. On the displayed page, click **Create VPC Endpoint**.

#. On the **Create VPC Endpoint** page, configure the parameters.


   .. figure:: /_static/images/en-us_image_0000001124400069.png
      :alt: **Figure 1** Create VPC Endpoint (**Service Category** set to **Cloud service**)

      **Figure 1** Create VPC Endpoint (**Service Category** set to **Cloud service**)


   .. figure:: /_static/images/en-us_image_0000001124315049.png
      :alt: **Figure 2** Create VPC Endpoint (**Service Category** set to **Find a service by name**)

      **Figure 2** Create VPC Endpoint (**Service Category** set to **Find a service by name**)

   .. table:: **Table 1** Required parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                           |
      +===================================+=======================================================================================================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is located. Resources in different regions cannot communicate with each other over internal networks. Select the nearest region for lower network latency and faster access to resources. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | There are two options as follows:                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | -  **Cloud services**: Select this value if the target VPC endpoint service is a cloud service.                                                                                                                                       |
      |                                   | -  **Find a service by name**: Select this value if the target VPC endpoint service is a private service of your own.                                                                                                                 |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service List                      | This parameter is available only when you select **Cloud services** for **Service Category**.                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | The VPC endpoint service has been created by operations people and you can use it without having to perform the creation operation.                                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC Endpoint Service Name         | This parameter is available only when you select **Find a service by name** for **Service Category**.                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | You can enter the VPC endpoint service name recorded in :ref:`Viewing Summary of a VPC Endpoint Service <vpcep_03_0102>` and click **Verify**.                                                                                        |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | -  If **Service name found** is displayed, proceed with subsequent operations.                                                                                                                                                        |
      |                                   | -  If **Service name not found** is displayed, check whether the region is the same as that of the connected VPC endpoint service or whether the entered service name is correct.                                                     |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private Domain Name               | If you want to access a VPC endpoint using a domain name, select **Create a Private Domain Name** when creating a VPC endpoint. After the VPC endpoint is created, you can access it using the domain name.                           |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | This parameter is only configured for interface VPC endpoints.                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | -  For the gateway type, this parameter is unavailable.                                                                                                                                                                               |
      |                                   | -  For the interface type, this parameter is optional.                                                                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is deployed.                                                                                                                                                                                 |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | This parameter is available when you want to access an interface endpoint service.                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Specifies the subnet where the VPC endpoint is located.                                                                                                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Private IP Address                | This parameter is available when you want to access an interface endpoint service.                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Specifies the private IP address of the VPC endpoint. You can select **Automatic** or **Manual**.                                                                                                                                     |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add a maximum of 20 tags to each VPC endpoint.                                                                                                           |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <en-us_topic_0131645189__table37259471306>`.                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | .. note::                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.                                                                                    |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0131645189__table37259471306:

   .. table:: **Table 2** Tag requirements for VPC endpoints

      +-----------------------------------+------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                            |
      +===================================+========================================================================+
      | Tag key                           | -  Cannot be left blank.                                               |
      |                                   | -  Must be unique for each resource.                                   |
      |                                   | -  Can contain a maximum of 36 Unicode characters.                     |
      |                                   | -  Can contain only letters, digits, hyphens (-), and underscores (_). |
      +-----------------------------------+------------------------------------------------------------------------+
      | Tag value                         | -  Cannot be left blank.                                               |
      |                                   | -  Can contain a maximum of 43 Unicode characters.                     |
      |                                   | -  Can contain only letters, digits, hyphens (-), and underscores (_). |
      +-----------------------------------+------------------------------------------------------------------------+

#. Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page and modify the parameters as needed, and click **Submit**.

.. _en-us_topic_0131645189__section3281125041216:

Creating a VPC Endpoint for Accessing Gateway VPC Endpoint Services
-------------------------------------------------------------------

#. Log in to the management console.

#. Click |image2| in the upper left corner and select the required region and project.

#. Choose **Service List** > **Networking** > **VPC Endpoint**.

#. On the displayed page, click **Create VPC Endpoint**.

#. On the **Create VPC Endpoint** page, configure the parameters.


   .. figure:: /_static/images/en-us_image_0000001124216445.png
      :alt: **Figure 3** Create VPC Endpoint (**Service Category** set to **Cloud service**)

      **Figure 3** Create VPC Endpoint (**Service Category** set to **Cloud service**)

   .. table:: **Table 3** Required parameters

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                           |
      +===================================+=======================================================================================================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is located. Resources in different regions cannot communicate with each other over internal networks. Select the nearest region for lower network latency and faster access to resources. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | Specifies the type of services that are configured as gateway VPC endpoint services. Only cloud services are supported.                                                                                                               |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Select **Cloud services**.                                                                                                                                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service List                      | This parameter is available only when you select **Cloud services** for **Service Category**.                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | In the VPC endpoint service list, select the VPC endpoint service whose type is gateway.                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | The VPC endpoint service has been created by operations people and you can use it without having to perform the creation operation.                                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is deployed.                                                                                                                                                                                 |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add a maximum of 20 tags to each VPC endpoint.                                                                                                           |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 4 <en-us_topic_0131645189__table62892050161211>`.                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   | .. note::                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                       |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.                                                                                    |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0131645189__table62892050161211:

   .. table:: **Table 4** Tag requirements for VPC endpoints

      +-----------------------------------+------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                            |
      +===================================+========================================================================+
      | Tag key                           | -  Cannot be left blank.                                               |
      |                                   | -  Must be unique for each resource.                                   |
      |                                   | -  Can contain a maximum of 36 Unicode characters.                     |
      |                                   | -  Can contain only letters, digits, hyphens (-), and underscores (_). |
      +-----------------------------------+------------------------------------------------------------------------+
      | Tag value                         | -  Cannot be left blank.                                               |
      |                                   | -  Can contain a maximum of 43 Unicode characters.                     |
      |                                   | -  Can contain only letters, digits, hyphens (-), and underscores (_). |
      +-----------------------------------+------------------------------------------------------------------------+

#. Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page and modify the parameters as needed, and click **Submit**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0289945877.png
