:original_name: vpcep_03_0102.html

.. _vpcep_03_0102:

Viewing Summary of a VPC Endpoint Service
=========================================

Scenarios
---------

This section describes how to query summary of a VPC endpoint service, including the name, ID, backend resource type, backend resource name, VPC, status, connection approval, service type, and creation time.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

   Locate the target VPC endpoint service by entering a filter in the search box in the upper right corner:

   -  Search by name or ID.

      a. Select **Name** or **ID** in the filter box.

      b. Enter a keyword in the search box.

      c. Click |image2| to start the search.

         VPC endpoint services containing the keyword are displayed in the list.

   -  Search by preset tag.

      a. Click |image3| in **Search by Tag**.


         .. figure:: /_static/images/en-us_image_0000001124311365.png
            :alt: **Figure 1** Searching by tag

            **Figure 1** Searching by tag

      b. Enter a tag and a value.

         Enter a key or value or select a key or value from the drop-down list.

         You can use a maximum of 20 tags to search for a VPC endpoint service.

      c. Click **Search**.

         The VPC endpoint service containing the specified tag is displayed in the list.

         If you set multiple tags, VPC endpoint services containing all the specified tags will be displayed.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name to view the details.


   .. figure:: /_static/images/en-us_image_0289945751.jpg
      :alt: **Figure 2** Summary of the VPC endpoint service

      **Figure 2** Summary of the VPC endpoint service

   :ref:`Table 1 <vpcep_03_0102__table11373229195910>` describes the parameters displayed on the VPC endpoint service details page.

   .. _vpcep_03_0102__table11373229195910:

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tab                   | Parameter             | Description                                                                                                                                                     |
      +=======================+=======================+=================================================================================================================================================================+
      | Summary               | Name                  | Specifies the name of the VPC endpoint service.                                                                                                                 |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | ID                    | Specifies the ID of the VPC endpoint service.                                                                                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Backend Resource Type | Specifies the type of the backend resource that provides services.                                                                                              |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Backend Resource Name | Specifies the name of the backend resource that provides services to be accessed.                                                                               |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | VPC                   | Specifies the VPC where the VPC endpoint service is deployed.                                                                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Status                | Specifies the status of the VPC endpoint service.                                                                                                               |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Connection Approval   | Specifies whether connection approval is required.                                                                                                              |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Service Type          | Specifies the type of the VPC endpoint service.                                                                                                                 |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Creation              | Specifies the creation time of the VPC endpoint service.                                                                                                        |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | VPC Endpoint ID       | Specifies the ID of the VPC endpoint.                                                                                                                           |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Packet ID             | Specifies the identifier of the VPC endpoint ID.                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Status                | Specifies the status of the VPC endpoint.                                                                                                                       |
      |                       |                       |                                                                                                                                                                 |
      |                       |                       | For details about statuses of VPC endpoint services and VPC endpoints, see :ref:`What Are Statuses of VPC Endpoint Services and VPC Endpoints? <vpcep_04_0005>` |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Owner                 | Specifies the domain ID of the VPC endpoint owner.                                                                                                              |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Creation              | Specifies the creation time of the VPC endpoint.                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Operation             | Specifies whether to allow a VPC endpoint to connect to a VPC endpoint service. The option can be **Accept** or **Reject**.                                     |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Permission Management | Authorized Domain ID  | Specifies the authorized domain ID for connecting to the VPC endpoint. The ID can also be \*.                                                                   |
      |                       |                       |                                                                                                                                                                 |
      |                       |                       | If you add an asterisk (``*``) to the whitelist, it means that all users can access the VPC endpoint service.                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Operation             | Specifies whether to delete an authorized domain from the whitelist.                                                                                            |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Mapping          | Protocol              | Specifies the protocol used for communications between the VPC endpoint service and VPC endpoint.                                                               |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Service Port          | Specifies the port provided by the backend service bound to the VPC endpoint service.                                                                           |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Terminal Port         | Specifies the port provided by the VPC endpoint, allowing you to access the VPC endpoint service.                                                               |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                   | Key                   | Specifies the tag key of the VPC endpoint service.                                                                                                              |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Value                 | Specifies the tag value of the VPC endpoint service.                                                                                                            |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Operation             | Specifies the operation to be performed on the VPC endpoint service tag, for example, you can select **Edit** or **Delete**.                                    |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0270653586.png
.. |image3| image:: /_static/images/en-us_image_0270653585.png
