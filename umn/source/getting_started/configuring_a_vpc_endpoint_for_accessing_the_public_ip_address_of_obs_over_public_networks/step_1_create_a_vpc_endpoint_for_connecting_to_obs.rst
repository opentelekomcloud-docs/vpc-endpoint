:original_name: vpcep_02_0402.html

.. _vpcep_02_0402:

Step 1: Create a VPC Endpoint for Connecting to OBS
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

4. On the **VPC Endpoints** page, click **Create VPC Endpoint**.

   The **Create VPC Endpoint** page is displayed.

   .. _vpcep_02_0402__vpcep_02_0303_fig1672316225376:

   .. figure:: /_static/images/en-us_image_0000001586069884.png
      :alt: **Figure 1** Create VPC Endpoint

      **Figure 1** Create VPC Endpoint

5. Configure required parameters.

   .. _vpcep_02_0402__vpcep_02_0303_table15408172022211:

   .. table:: **Table 1** VPC endpoint parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                          |
      +===================================+======================================================================================================================================================+
      | Region                            | Specifies the region where the VPC endpoint is to be located.                                                                                        |
      |                                   |                                                                                                                                                      |
      |                                   | Resources in different regions cannot communicate with each other over an intranet. For lower latency and quicker access, select the nearest region. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service Category                  | There are two options:                                                                                                                               |
      |                                   |                                                                                                                                                      |
      |                                   | -  **Cloud services**: Select this value if the target VPC endpoint service is a cloud service.                                                      |
      |                                   | -  **Find a service by name**: Select this value if the target VPC endpoint service is a private service of your own.                                |
      |                                   |                                                                                                                                                      |
      |                                   | In this example, select **Cloud services**.                                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Service List                      | This parameter is available only when you select **Cloud services** for **Service Category**.                                                        |
      |                                   |                                                                                                                                                      |
      |                                   | The VPC endpoint service has been created by the O&M personnel and you can directly use it.                                                          |
      |                                   |                                                                                                                                                      |
      |                                   | Select **com.t-systems.otc.eu-nl.obs-internet**.                                                                                                     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | VPC                               | Specifies the VPC where the VPC endpoint is to be deployed.                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subnet                            | Specifies the subnet where the VPC endpoint is to be located.                                                                                        |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | (Optional) Specifies the VPC endpoint tag, which consists of a key and a value. You can add a maximum of 20 tags to each VPC endpoint.               |
      |                                   |                                                                                                                                                      |
      |                                   | Tag keys and values must meet requirements listed in :ref:`Table 2 <vpcep_02_0402__vpcep_02_0303_table1487920102215>`.                               |
      |                                   |                                                                                                                                                      |
      |                                   | .. note::                                                                                                                                            |
      |                                   |                                                                                                                                                      |
      |                                   |    If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.                                         |
      |                                   |                                                                                                                                                      |
      |                                   |    For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_02_0402__vpcep_02_0303_table1487920102215:

   .. table:: **Table 2** Tag requirements for VPC endpoints

      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                                          |
      +===================================+======================================================================================+
      | Key                               | -  Cannot be left blank.                                                             |
      |                                   | -  Must be unique for each resource.                                                 |
      |                                   | -  Can contain a maximum of 36 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Value                             | -  Cannot be left blank.                                                             |
      |                                   | -  Can contain a maximum of 43 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+

6. .. _vpcep_02_0402__li20290450181218:

   Confirm the specifications and click **Create Now**.

   -  If all of the specifications are correct, click **Submit**.
   -  If any of the specifications are incorrect, click **Previous** to return to the previous page and modify the parameters as needed, and click **Submit**.

7. Click **Back to VPC Endpoint List** after the task is submitted.

   If the status of the VPC endpoint changes from **Creating** to **Accepted**, the VPC endpoint for connecting to **com.t-systems.otc.eu-nl.obs-internet** is created.

8. In the VPC endpoint list, click the ID of the target VPC endpoint to view its details.


   .. figure:: /_static/images/en-us_image_0000001124529567.png
      :alt: **Figure 2** Summary of the VPC endpoint

      **Figure 2** Summary of the VPC endpoint

.. |image1| image:: /_static/images/en-us_image_0289945877.png
