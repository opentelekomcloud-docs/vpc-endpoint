:original_name: vpcep_06_0304.html

.. _vpcep_06_0304:

Querying Details of a VPC Endpoint
==================================

Function
--------

This API is used to query details of a VPC endpoint.

URI
---

GET /v1/{project_id}/vpc-endpoints/{vpc_endpoint_id}

:ref:`Table 1 <vpcep_06_0304__table22005568>` describes the required parameters.

.. _vpcep_06_0304__table22005568:

.. table:: **Table 1** Parameter description

   +-----------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory | Description                                                                                                                    |
   +=================+===========+================================================================================================================================+
   | project_id      | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003_0>`. |
   +-----------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_id | Yes       | Specifies the ID of the VPC endpoint.                                                                                          |
   +-----------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  Example request

   This request is to query details of the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed83**.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoints/4189d3c2-8882-4871-a3c2-d380272eed83

Response
--------

-  Parameter description

   .. table:: **Table 2** Response parameters

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint.                                                                                                                                                                     |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_type          | String                | Specifies the type of the VPC endpoint service that is associated with the VPC endpoint.                                                                                                                         |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  Gateway: VPC endpoint services of this type are configured by operations people. You can use them directly without the need to create one by yourselves.                                                      |
      |                       |                       | -  Interface: VPC endpoint services of this type include cloud services configured by operations people and private services created by yourselves. You cannot configure these cloud services, but can use them. |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the connection status of the VPC endpoint.                                                                                                                                                             |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **pendingAcceptance**: indicates that the VPC endpoint is pending acceptance.                                                                                                                                 |
      |                       |                       | -  **creating**: indicates the VPC endpoint is being created.                                                                                                                                                    |
      |                       |                       | -  **accepted**: indicates the VPC endpoint has been accepted.                                                                                                                                                   |
      |                       |                       | -  **rejected**: indicates the VPC endpoint has been rejected.                                                                                                                                                   |
      |                       |                       | -  **failed**: indicates the creation of the VPC endpoint failed.                                                                                                                                                |
      |                       |                       | -  **deleting**: indicates the VPC endpoint is being deleted.                                                                                                                                                    |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | active_status         | String                | Specifies the domain status.                                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **frozen**: indicates that the domain is frozen.                                                                                                                                                              |
      |                       |                       | -  **active**: indicates that the domain is normal.                                                                                                                                                              |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | endpoint_service_name | String                | Specifies the name of the VPC endpoint service.                                                                                                                                                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | marker_id             | Integer               | Specifies the packet ID of the VPC endpoint.                                                                                                                                                                     |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | endpoint_service_id   | String                | Specifies the ID of the VPC endpoint service.                                                                                                                                                                    |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enable_dns            | Boolean               | Specifies whether to create a private domain name.                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **true**: indicates that a private domain name is created.                                                                                                                                                    |
      |                       |                       | -  **false**: indicates that a private domain name is not created.                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    When a VPC endpoint for connecting to a gateway VPC endpoint service is created, no private domain name is created no matter **enable_dns** is set to **true** or **false**.                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dns_names             | Array of strings      | Specifies the domain name for accessing the associated VPC endpoint service.                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This parameter is only available when **enable_dns** is set to **true**.                                                                                                                                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ip                    | String                | Specifies the IP address for accessing the associated VPC endpoint service.                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This parameter is returned only under the following conditions:                                                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  You query a VPC endpoint for accessing an interface VPC endpoint service.                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  The connection approval function is enabled for the VPC endpoint service, and the connection has been approved.                                                                                               |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    The status of the VPC endpoint can be **Accepted** or **Rejected**. The **Rejected** status only appears when the VPC endpoint is accepted and then rejected.                                                 |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | vpc_id                | String                | Specifies the ID of the VPC where the VPC endpoint is to be created.                                                                                                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | subnet_id             | String                | Specifies the ID of the subnet in the VPC specified by **vpc_id**. The ID is in the UUID format.                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This parameter is available only if you create a VPC endpoint for connecting to an interface VPC endpoint service.                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint.                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the update time of the VPC endpoint.                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | project_id            | String                | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003_0>`.                                                                                   |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tags                  | Array of objects      | Lists the resource tags. For details, see :ref:`Table 3 <vpcep_06_0304__table489217571060>`.                                                                                                                     |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | error                 | Array of objects      | Specifies the error message.                                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This field is returned when the status of the VPC endpoint changes to **failed**. For details, see :ref:`Table 4 <vpcep_06_0304__table14419242754>`.                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | whitelist             | Array of strings      | Specifies the whitelist for controlling access to the VPC endpoint.                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | If you do not specify this parameter, an empty whitelist is returned.                                                                                                                                            |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This parameter is available only if you create a VPC endpoint for connecting to an interface VPC endpoint service.                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enable_whitelist      | Boolean               | Specifies whether to enable access control.                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **true**: indicates that access control is enabled.                                                                                                                                                           |
      |                       |                       | -  **false**: indicates that access control is disabled.                                                                                                                                                         |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | If you do not specify this parameter, the whitelist is not enabled.                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This parameter is available only if you create a VPC endpoint for connecting to an interface VPC endpoint service.                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | routetables           | Array of strings      | Lists the IDs of route tables.                                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | If you do not specify this parameter, the route table ID of the VPC is returned.                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This parameter is available only when you create a VPC endpoint for connecting to a gateway VPC endpoint service.                                                                                                |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0304__table489217571060:

   .. table:: **Table 3** **ResourceTags** parameters

      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                               |
      +===========+========+===========================================================================================================================================================================================+
      | key       | String | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters. This parameter cannot be left blank. It can contain only digits, letters, hyphens (-), and underscores (_). |
      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the tag value. A tag value contains a maximum of 43 Unicode characters and can be left blank. It can contain only digits, letters, hyphens (-), and underscores (_).            |
      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0304__table14419242754:

   .. table:: **Table 4** Error parameters

      ============= ====== ============================
      Parameter     Type   Description
      ============= ====== ============================
      error_code    String Specifies the error code.
      error_message String Specifies the error message.
      ============= ====== ============================

-  Example response

   .. code-block::

      {
          "id": "4189d3c2-8882-4871-a3c2-d380272eed83",
          "service_type": "interface",
          "marker_id": 322312312312,
          "status": "accepted",
          "vpc_id": "4189d3c2-8882-4871-a3c2-d380272eed83",
          "enable_dns": false,
          "endpoint_service_name": "test123",
          "endpoint_service_id": "test123",
          "project_id": "6e9dfd51d1124e8d8498dce894923a0d",
          "whitelist": [
              "127.0.0.1"
          ],
          "enable_whitelist": true,
          "created_at": "2018-01-30T07:42:01.174",
          "update_at": "2018-01-30T07:42:01.174",
          "tags": [
              {
                  "key": "test1",
                  "value": "test1"
              }
          ]
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
