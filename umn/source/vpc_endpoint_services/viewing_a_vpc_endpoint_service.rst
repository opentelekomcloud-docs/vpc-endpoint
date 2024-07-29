:original_name: vpcep_03_0102.html

.. _vpcep_03_0102:

Viewing a VPC Endpoint Service
==============================

Scenarios
---------

This section describes how to query details of a VPC endpoint service, including its name, ID, backend resource type, backend resource name, VPC, status, connection approval, service type, and creation time.

.. _vpcep_03_0102__section15309424142016:

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

   Locate the VPC endpoint service by entering a filter in the search box in the upper right corner:

   -  Search by name or ID.

      a. Select **Name** or **ID** in the filter box.

      b. Enter a keyword in the search box.

      c. Click |image2| to start the search.

         VPC endpoint services containing the keyword are displayed.

   -  Search by tag.

      a. Click the filter box and select **Tag** from the drop-down list.


         .. figure:: /_static/images/en-us_image_0000001963151878.png
            :alt: **Figure 1** Searching for VPC endpoint services by tag

            **Figure 1** Searching for VPC endpoint services by tag

      b. Select tags.


         .. figure:: /_static/images/en-us_image_0000001963155370.png
            :alt: **Figure 2** Selecting tags

            **Figure 2** Selecting tags

      c. Click **OK** to search.

         VPC endpoint services containing the specified tags are displayed.

5. In the VPC endpoint service list, locate the VPC endpoint service and click its name to view its details.

   .. _vpcep_03_0102__fig148852011125319:

   .. figure:: /_static/images/en-us_image_0000001949612440.png
      :alt: **Figure 3** Summary of the VPC endpoint service

      **Figure 3** Summary of the VPC endpoint service

   :ref:`Table 1 <vpcep_03_0102__table11373229195910>` describes the parameters displayed on the VPC endpoint service details page.

   .. _vpcep_03_0102__table11373229195910:

   .. table:: **Table 1** Parameters contained in the details of a VPC endpoint service

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tab                   | Parameter             | Description                                                                                                                                           |
      +=======================+=======================+=======================================================================================================================================================+
      | Summary               | Name                  | Specifies the name of the VPC endpoint service.                                                                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | ID                    | Specifies the ID of the VPC endpoint service.                                                                                                         |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Backend Resource Type | Specifies the type of the backend resource that provides services.                                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Backend Resource Name | Specifies the name of the backend resource that provides services to be accessed.                                                                     |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | VPC                   | Specifies the VPC where the VPC endpoint service is to be deployed.                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Status                | Specifies the status of the VPC endpoint service.                                                                                                     |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Connection Approval   | Specifies whether connection approval is required.                                                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Service Type          | Specifies the type of the VPC endpoint service.                                                                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Created               | Specifies the creation time of the VPC endpoint service.                                                                                              |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | VPC Endpoint ID       | Specifies the ID of the VPC endpoint.                                                                                                                 |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | Packet ID             | Specifies the identifier of the VPC endpoint ID.                                                                                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | Status                | Specifies the status of the VPC endpoint.                                                                                                             |
      |                       |                       |                                                                                                                                                       |
      |                       |                       | For details about the statuses of a VPC endpoint, see :ref:`What Statuses Are Available for a VPC Endpoint Service and VPC Endpoint? <vpcep_04_0005>` |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | Owner                 | Specifies the account ID of the VPC endpoint owner.                                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | Created               | Specifies the creation time of the VPC endpoint.                                                                                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connection Management | Operation             | Specifies whether to allow a VPC endpoint to connect to a VPC endpoint service. The option can be **Accept** or **Reject**.                           |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Permission Management | Authorized Account ID | Specifies the authorized account ID for connecting to the VPC endpoint. The ID can also be \*.                                                        |
      |                       |                       |                                                                                                                                                       |
      |                       |                       | If you add an asterisk (``*``) to the whitelist, it means that all users can access the VPC endpoint service.                                         |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Permission Management | Operation             | Specifies whether to delete an authorized account from the whitelist.                                                                                 |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Mapping          | Protocol              | Specifies the protocol used for communications between the VPC endpoint service and a VPC endpoint.                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Mapping          | Service Port          | Specifies the port provided by the backend service bound to the VPC endpoint service.                                                                 |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Port Mapping          | Terminal Port         | Specifies the port provided by the VPC endpoint, allowing you to access the VPC endpoint service.                                                     |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  | Key                   | Specifies the tag key of the VPC endpoint service.                                                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  | Value                 | Specifies the tag value of the VPC endpoint service.                                                                                                  |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  | Operation             | Specifies the operation to be performed on the VPC endpoint service tag. You can click **Edit** or **Delete**.                                        |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
.. |image2| image:: /_static/images/en-us_image_0000001979891941.png
