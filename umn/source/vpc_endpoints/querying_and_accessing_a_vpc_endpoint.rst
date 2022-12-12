:original_name: vpcep_03_0202.html

.. _vpcep_03_0202:

Querying and Accessing a VPC Endpoint
=====================================

Scenarios
---------

After a VPC endpoint is created, you can query its details and access it.

Querying a VPC Endpoint
-----------------------

Perform the following operations to query details about a VPC endpoint, including the ID, associated VPC endpoint service name, VPC, and status.

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

   On the displayed page, locate the target VPC endpoint by entering a keyword in the search box in the upper right corner:

   -  Search by VPC endpoint service name or VPC endpoint ID.

      a. Select **VPC endpoint service name** or **ID** in the filter box.

      b. Enter a keyword in the search box.

      c. Click |image2| to start the search.

         VPC endpoints containing the keyword are displayed in the VPC endpoint list.

   -  Search by preset tag.

      a. Click |image3| in **Search by Tag**.


         .. figure:: /_static/images/en-us_image_0000001124400993.png
            :alt: **Figure 1** Searching by tag

            **Figure 1** Searching by tag

      b. Enter a tag and a value.

         Enter a key or value or select a key or value from the drop-down list.

         You can use a maximum of 20 tags to search for a VPC endpoint.

      c. Click **Search**.

         VPC endpoints containing the specified tag are displayed in the VPC endpoint list.

         If you set multiple tags, VPC endpoints containing all the specified tags will be displayed.

4. In the VPC endpoint list, click the ID of the target VPC endpoint to view its details.

   After an interface VPC endpoint is created, a private IP address is assigned together with a private domain name if you select **Create a Private Domain Name**.


   .. figure:: /_static/images/en-us_image_0289945778.png
      :alt: **Figure 2** Summary of the VPC endpoint

      **Figure 2** Summary of the VPC endpoint

   .. table:: **Table 1** Parameter description

      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      | Tab     | Parameter                 | Description                                                                                                          |
      +=========+===========================+======================================================================================================================+
      | Summary | ID                        | Specifies the ID of the VPC endpoint.                                                                                |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | VPC                       | Specifies the VPC where the VPC endpoint is deployed.                                                                |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | VPC Endpoint Service Name | Specifies the name of the VPC endpoint service that the VPC endpoint is used to access.                              |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Private IP Address        | Specifies the IP address for accessing the VPC endpoint.                                                             |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Private Domain Name       | Specifies the private domain name for accessing the VPC endpoint.                                                    |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Status                    | Specifies the status of the VPC endpoint.                                                                            |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Type                      | Specifies the type of the VPC endpoint service that the VPC endpoint is used to access.                              |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Created                   | Specifies the creation time of the VPC endpoint.                                                                     |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      | Tags    | Key                       | Specifies the tag key of the VPC endpoint.                                                                           |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Value                     | Specifies the tag value of the VPC endpoint.                                                                         |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+
      |         | Operation                 | Specifies the operation to be performed on the VPC endpoint tag, for example, you can select **Edit** or **Delete**. |
      +---------+---------------------------+----------------------------------------------------------------------------------------------------------------------+

Accessing a VPC Endpoint Using a Private IP Address
---------------------------------------------------

Perform the following operations to access a VPC endpoint using its private IP address:

#. In the VPC that the VPC endpoint belongs to, log in to the backend resource, for example, an ECS.

#. Select a command based on the backend resource type and run the command to access the VPC endpoint. The command format is as follows:

   *Command* *Private IP address*:*Port number*

   The following is a command example:

   **curl** *Private IP address:Port number*

Accessing a VPC Endpoint (Using a Private Domain Name)
------------------------------------------------------

You can access a VPC endpoint using its private domain name if you select **Create a Private Domain Name** when creating the endpoint.

The system automatically creates a private zone for the generated domain name and adds A record set for the private zone to resolve the domain name into the private IP address of the VPC endpoint.

You can view the corresponding private zone and its resolution records on the DNS console. For more information, see `Configuring a Private Zone <https://docs.otc.t-systems.com/en-us/usermanual/dns/dns_qs_0006.html>`__.

**Viewing the record set of the private domain name**

#. Log in to the management console.

#. In the service list, choose **Network** > **Domain Name Service**.

   The DNS console is displayed.

#. In the navigation pane, choose **Private Zones**.

   The **Private Zones** page is displayed.

4. In the private zone list, click the name of the target private zone.

   The record set page is displayed.

5. In the record set list, locate the target A record set and view its information.

   When **Status** changes to **Normal**, the resolution takes effect.


   .. figure:: /_static/images/en-us_image_0289945896.png
      :alt: **Figure 3** Record set of the private domain name

      **Figure 3** Record set of the private domain name

**Accessing a VPC endpoint using a private domain name**

#. In the VPC that the VPC endpoint belongs to, log in to the backend resource, for example, an ECS.

#. Select a command based on the backend resource type and run the command to access the VPC endpoint. The command format is as follows:

   *Command* *Private domain name*:*Port number*

   The following is a command example:

   **curl** *Private domain name:Port number*

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0270653586.png
.. |image3| image:: /_static/images/en-us_image_0270653585.png
