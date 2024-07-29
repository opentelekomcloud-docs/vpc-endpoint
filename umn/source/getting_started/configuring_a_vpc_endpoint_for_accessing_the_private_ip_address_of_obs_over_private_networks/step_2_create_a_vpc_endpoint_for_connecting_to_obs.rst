:original_name: vpcep_02_0303.html

.. _vpcep_02_0303:

Step 2: Create a VPC Endpoint for Connecting to OBS
===================================================

Scenarios
---------

This section describes how to create a VPC endpoint to access OBS from an on-premises data center.

Prerequisites
-------------

The required VPC endpoint service is available.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the required region and project.

#. Click **Service List** and choose **Networking** > **VPC Endpoint**.

#. On the **VPC Endpoints** page, click **Create VPC Endpoint**.

   The **Create VPC Endpoint** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001949673460.png
      :alt: **Figure 1** Create VPC Endpoint

      **Figure 1** Create VPC Endpoint

#. Configure VPC endpoint parameters.

   .. _vpcep_02_0303__table15408172022211:

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
      |                                   | Example: **com.t-systems.otc.eu-de.obs**                                                                                                             |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is to be deployed.                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | Specifies the subnet where the VPC endpoint is to be deployed.                                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Route Table                       | This parameter is available only when you create a VPC endpoint for connecting to a gateway VPC endpoint service.                                    |
      |                                   |                                                                                                                                                      |
      |                                   | Select a route table for the VPC where the VPC endpoint is to be deployed.                                                                           |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | This parameter is optional.                                                                                                                          |
      |                                   |                                                                                                                                                      |
      |                                   | Specifies the VPC endpoint tag, which consists of a key and a value. You can add up to 20 tags to each VPC endpoint.                                 |
      |                                   |                                                                                                                                                      |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <vpcep_02_0303__table1487920102215>`.                                             |
      |                                   |                                                                                                                                                      |
      |                                   | .. note::                                                                                                                                            |
      |                                   |                                                                                                                                                      |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                         |
      |                                   |                                                                                                                                                      |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_02_0303__table1487920102215:

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

#. .. _vpcep_02_0303__li20290450181218:

   Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page and modify the parameters as needed, and click **Submit**.

#. Click **Back to VPC Endpoint List** after the task is submitted.

   If the status of the VPC endpoint changes from **Creating** to **Accepted**, the VPC endpoint for connecting to **com.t-systems.otc.eu-de.obs** is created.

#. In the VPC endpoint list, click the ID of the VPC endpoint to view its details.


   .. figure:: /_static/images/en-us_image_0000001979891821.png
      :alt: **Figure 2** Summary of the VPC endpoint

      **Figure 2** Summary of the VPC endpoint

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
