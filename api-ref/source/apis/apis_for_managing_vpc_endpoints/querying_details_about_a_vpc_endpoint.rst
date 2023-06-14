:original_name: vpcep_06_0304.html

.. _vpcep_06_0304:

Querying Details About a VPC Endpoint
=====================================

Function
--------

This API is used to query details about a VPC endpoint.

URI
---

GET /v1/{project_id}/vpc-endpoints/{vpc_endpoint_id}

:ref:`Table 1 <vpcep_06_0304__table22005568>` describes parameters in this URI.

.. _vpcep_06_0304__table22005568:

.. table:: **Table 1** URI parameters

   +-----------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory | Description                                                                                                                  |
   +=================+===========+==============================================================================================================================+
   | project_id      | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +-----------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_id | Yes       | Specifies the ID of the VPC endpoint.                                                                                        |
   +-----------------+-----------+------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  Example request

   This request is to query details about the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed83**.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoints/4189d3c2-8882-4871-a3c2-d380272eed83

Response
--------

-  Parameter description

   .. _vpcep_06_0304__table37620597:

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
      |                       |                       | -  **pendingAcceptance**: The VPC endpoint is to be accepted.                                                                                                                                                    |
      |                       |                       | -  **creating**: The VPC endpoint is being created.                                                                                                                                                              |
      |                       |                       | -  **accepted**: The VPC endpoint has been accepted.                                                                                                                                                             |
      |                       |                       | -  **rejected**: The VPC endpoint has been rejected.                                                                                                                                                             |
      |                       |                       | -  **failed**: The VPC endpoint failed to be created.                                                                                                                                                            |
      |                       |                       | -  **deleting**: The VPC endpoint is being deleted.                                                                                                                                                              |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | active_status         | Array of strings      | Specifies the domain status.                                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **arrear_frozen**: frozen due to arrears                                                                                                                                                                      |
      |                       |                       | -  **verify_frozen**: frozen due to lack of real-name authentication                                                                                                                                             |
      |                       |                       | -  **police_frozen**: frozen for legal management                                                                                                                                                                |
      |                       |                       | -  **illegal_frozen**: frozen due to abuse                                                                                                                                                                       |
      |                       |                       | -  **partner_frozen**: frozen for partnership                                                                                                                                                                    |
      |                       |                       | -  **active**: The domain is normal.                                                                                                                                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | endpoint_service_name | String                | Specifies the name of the VPC endpoint service.                                                                                                                                                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | marker_id             | Integer               | Specifies the packet ID of the VPC endpoint.                                                                                                                                                                     |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | endpoint_service_id   | String                | Specifies the ID of the VPC endpoint service.                                                                                                                                                                    |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enable_dns            | Boolean               | Specifies whether to create a private domain name.                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **true**: A private domain name is created.                                                                                                                                                                   |
      |                       |                       | -  **false**: A private domain name is not created.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    When a VPC endpoint for connecting to a gateway VPC endpoint service is created, no private domain name is created no matter **enable_dns** is set to **true** or **false**.                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dns_names             | Array of strings      | Specifies the domain name for accessing the associated VPC endpoint service.                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service and **enable_dns** is set to **true**.                                                    |
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
      | subnet_id             | String                | Specifies the ID of the subnet in the VPC specified by **vpc_id**. The ID is in UUID format.                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                                                                          |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint.                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the update time of the VPC endpoint.                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | project_id            | String                | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`.                                                                                     |
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
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                                                                          |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enable_whitelist      | Boolean               | Specifies whether access control is enabled.                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **true**: Access control is enabled.                                                                                                                                                                          |
      |                       |                       | -  **false**: Access control is disabled.                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | If you do not specify this parameter, the whitelist is not enabled.                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    This parameter is available only when you create a VPC endpoint for connecting to an interface VPC endpoint service.                                                                                          |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | routetables           | Array of strings      | Lists the IDs of route tables.                                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | If you do not specify this parameter, the route table ID of the VPC is returned.                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       |    This parameter is available only when you create a VPC endpoint for connecting to a gateway VPC endpoint service.                                                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | description           | String                | Specifies the description of the VPC endpoint.                                                                                                                                                                   |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | specification_name    | String                | Specifies the name of the VPC endpoint specifications.                                                                                                                                                           |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | endpoint_pool_id      | String                | (To be discarded) Specifies the ID of the cluster associated with the VPC endpoint.                                                                                                                              |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enable_status         | String                | Specifies whether to enable the endpoint.                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **enable**: The endpoint will be enabled.                                                                                                                                                                     |
      |                       |                       | -  **disable**: The endpoint will be disabled.                                                                                                                                                                   |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0304__table489217571060:

   .. table:: **Table 3** Tags parameters

      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                                      |
      +===========+========+==================================================================================================================================================================================================+
      | key       | String | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters. **key** cannot be left blank. It can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the tag value. A tag value contains a maximum of 43 Unicode characters and can be left blank. It can contain only digits, letters, hyphens (-), underscores (_), and at signs (@).     |
      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0304__table14419242754:

   .. table:: **Table 4** Error parameters

      ============= ====== ============================
      Parameter     Type   Description
      ============= ====== ============================
      error_code    String Specifies the error code.
      error_message String Specifies the error message.
      ============= ====== ============================

-  .. _vpcep_06_0304__li63811541:

   Example response

   .. code-block::

      {
          "id": "4189d3c2-8882-4871-a3c2-d380272eed83",
          "status": "accepted",
          "service_type": "interface",
          "marker_id": 322312312312,
          "active_status":[
                          "active"
          ],
          "vpc_id": "4189d3c2-8882-4871-a3c2-d380272eed83",
          "enable_dns": false,
          "endpoint_service_name": "test123",
          "endpoint_service_id": "test123",
          "project_id": "6e9dfd51d1124e8d8498dce894923a0d",
          "whitelist": [
              "127.0.0.1"
          ],
          "enable_whitelist": true,
          "specification_name":"default",
          "endpoint_pool_id":"501f4a3b-6f96-4309-97d1-e291b8ca5b96",
          "description":"demo",
          "created_at": "2018-01-30T07:42:01Z",
          "updated_at": "2018-01-30T07:42:01Z",
          "description" : "",
          "tags": [
              {
                  "key": "test1",
                  "value": "test1"
              }
          ]
      }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
