:original_name: vpcep_03_0202.html

.. _vpcep_03_0202:

Querying and Accessing a VPC Endpoint
=====================================

Scenarios
---------

After a VPC endpoint is created, you can query its details and access it.

Constraints
-----------

One VPC endpoint supports up to 3,000 concurrent connections.

.. _vpcep_03_0202__section19334124820566:

Querying a VPC Endpoint
-----------------------

You can query details of a VPC endpoint, including its ID, VPC, VPC endpoint service name, creation time, private domain name, status, type, IPv4 address, access control, and description.

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

   On the displayed page, locate the VPC endpoint by entering a keyword in the upper search box:

   -  Search for a VPC endpoint by parameters including **ID**, **VPC**, **VPC ID**, **Status**, **VPC Endpoint Service Name**, **Type**, **IPv4**, **Created**, or **Description**. Take **ID** or **VPC Endpoint Service Name** as an example.

      a. Select **ID** or **VPC Endpoint Service Name** in the filter box.


         .. figure:: /_static/images/en-us_image_0000002184555045.png
            :alt: **Figure 1** Searching by ID or VPC endpoint service name

            **Figure 1** Searching by ID or VPC endpoint service name

      b. Enter a keyword in the search box.


         .. figure:: /_static/images/en-us_image_0000002149398074.png
            :alt: **Figure 2** Entering a keyword for search

            **Figure 2** Entering a keyword for search

      c. Press Enter to start searching.

         VPC endpoints containing the keyword are displayed in the VPC endpoint list.

   -  Search by tag.

      a. Click the filter box and select keys from the drop-down list.


         .. figure:: /_static/images/en-us_image_0000002184558693.png
            :alt: **Figure 3** Selecting tag keys

            **Figure 3** Selecting tag keys

      b. Select tag values for the selected tag keys.


         .. figure:: /_static/images/en-us_image_0000002149399690.png
            :alt: **Figure 4** Selecting tag values

            **Figure 4** Selecting tag values

      c. View the search result.

         The VPC endpoint list displays the VPC endpoints that match the specified tags.

4. In the VPC endpoint list, click the ID of the VPC endpoint to view its details.

   After an interface VPC endpoint is created, an IPv4 address is assigned together with a private domain name if you select **Create a Private Domain Name**.

   .. _vpcep_03_0202__fig735142618538:

   .. figure:: /_static/images/en-us_image_0000002149315270.png
      :alt: **Figure 5** **Summary** of the VPC endpoint (for accessing an interface VPC endpoint service)

      **Figure 5** **Summary** of the VPC endpoint (for accessing an interface VPC endpoint service)


   .. figure:: /_static/images/en-us_image_0000002184637917.png
      :alt: **Figure 6** **Summary** of the VPC endpoint (for accessing a gateway VPC endpoint service)

      **Figure 6** **Summary** of the VPC endpoint (for accessing a gateway VPC endpoint service)

   .. table:: **Table 1** Parameters contained in the details of a VPC endpoint

      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Tab                   | Parameter                 | Description                                                                                                                    |
      +=======================+===========================+================================================================================================================================+
      | Summary               | ID                        | Specifies the ID of the VPC endpoint.                                                                                          |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | VPC                       | Specifies the VPC where the VPC endpoint is deployed.                                                                          |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | VPC Endpoint Service Name | Specifies the name of the VPC endpoint service that the VPC endpoint is used to access.                                        |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | IPv4 Address              | Specifies the IPv4 address of the VPC endpoint.                                                                                |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Private Domain Name       | Specifies the private domain name for accessing the VPC endpoint.                                                              |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Status                    | Specifies the status of the VPC endpoint.                                                                                      |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Type                      | Specifies the type of the VPC endpoint service that the VPC endpoint is used to access.                                        |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Created                   | Specifies the creation time of the VPC endpoint.                                                                               |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Access Control            | Specifies whether the whitelist is enabled for IP addresses to access this VPC endpoint.                                       |
      |                       |                           |                                                                                                                                |
      |                       |                           | -  If **Access Control** is enabled, only IP addresses or CIDR blocks in the whitelist are allowed to access the VPC endpoint. |
      |                       |                           | -  If **Access Control** is disabled, any IP address or CIDR block can access the VPC endpoint.                                |
      |                       |                           |                                                                                                                                |
      |                       |                           | .. note::                                                                                                                      |
      |                       |                           |                                                                                                                                |
      |                       |                           |    Access control can be enabled only for VPC endpoints for connecting to an interface VPC endpoint service.                   |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Summary               | Description               | Provides supplementary information about the VPC endpoint.                                                                     |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Access Control        | IP Address or CIDR Block  | Specifies the IP addresses and CIDR blocks that are allowed to access the VPC endpoint.                                        |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Access Control        | Operation                 | Specifies the operation to be performed on whitelist records of the VPC endpoint. Only deletion is supported.                  |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Route Tables          | Name/ID                   | Specifies the name or ID of the route table.                                                                                   |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Route Tables          | VPC                       | Specifies the VPC that the route table belongs to.                                                                             |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Route Tables          | Type                      | Specifies the type of the route table, which can be **Default** and **Custom**.                                                |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Route Tables          | Associated Subnets        | Specifies the number of subnets associated with the route table.                                                               |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Route Tables          | Operation                 | Specifies the operation to be performed on the route table. The operation can be **Disassociate** or **Associate**.            |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  | Key                       | Specifies the tag key of the VPC endpoint.                                                                                     |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  | Value                     | Specifies the tag value of the VPC endpoint.                                                                                   |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Tags                  | Operation                 | Specifies the operation to be performed on the VPC endpoint tag. You can click **Edit** or **Delete**.                         |
      +-----------------------+---------------------------+--------------------------------------------------------------------------------------------------------------------------------+

   .. note::

      -  The **Access Control** tab is displayed only for VPC endpoints for connecting to interface VPC endpoint services.
      -  The **Route Tables** tab is displayed only for VPC endpoints for connecting to gateway VPC endpoint services.

Accessing a VPC Endpoint via Its Private IP Address
---------------------------------------------------

Perform the following operations to access a VPC endpoint via its private IP address:

#. In the VPC where the VPC endpoint is deployed, log in to the backend resource, for example, an ECS.

#. Select a command based on the backend resource type and run the command to access the VPC endpoint. The command format is as follows:

   *Command* *Private IP address*:*Port number*

   The following is a command example:

   **curl** *Private IP address:Port number*

Accessing a VPC Endpoint (via Its Private Domain Name)
------------------------------------------------------

You can access a VPC endpoint via its private domain name if you select **Create a Private Domain Name** when creating the VPC endpoint.

The system automatically creates a private zone for the generated domain name and adds an A record set for the private zone to resolve the domain name into the private IP address of the VPC endpoint.

You can view the corresponding private zone and its resolution records on the DNS console. For more information, see `Configuring a Private Zone <https://docs.otc.t-systems.com/en-us/usermanual/dns/dns_qs_0006.html>`__.

**Viewing the record set of the private domain name**

#. Log in to the management console.

#. In the service list, choose **Network** > **Domain Name Service**.

   The DNS console is displayed.

#. In the navigation pane, choose **Private Zones**.

   The **Private Zones** page is displayed.

4. In the private zone list, click the name of the private zone.

   The **Record Sets** page is displayed.

5. In the record set list, locate the A record set and view its information.

   When **Status** changes to **Normal**, the resolution takes effect.


   .. figure:: /_static/images/en-us_image_0000001979891945.png
      :alt: **Figure 7** Record set of the private domain name

      **Figure 7** Record set of the private domain name

**Accessing a VPC endpoint via its private domain name**

#. In the VPC where the VPC endpoint is deployed, log in to the backend resource, for example, an ECS.

#. Select a command based on the backend resource type and run the command to access the VPC endpoint. The command format is as follows:

   *Command* *Private domain name*:*Port number*

   The following is a command example:

   **curl** *Private domain name:Port number*

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
