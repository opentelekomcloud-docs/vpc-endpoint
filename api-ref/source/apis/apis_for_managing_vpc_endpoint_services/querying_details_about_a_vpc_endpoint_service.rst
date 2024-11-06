:original_name: vpcep_06_0202.html

.. _vpcep_06_0202:

Querying Details About a VPC Endpoint Service
=============================================

Function
--------

This API is used to query details about a VPC endpoint service.

URI
---

GET /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}

:ref:`Table 1 <vpcep_06_0202__d0e2452>` describes parameters in this URI.

.. _vpcep_06_0202__d0e2452:

.. table:: **Table 1** URI parameters

   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Mandatory | Description                                                                                                                  |
   +=========================+===========+==============================================================================================================================+
   | project_id              | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_service_id | Yes       | Specifies the ID of the VPC endpoint service.                                                                                |
   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  Example request

   This request is to query details about the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88

Response
--------

-  Parameter description

   .. _vpcep_06_0202__d0e2596:

   .. table:: **Table 2** Response parameters

      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                                                                       |
      +=======================+=======================+===================================================================================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint service.                                                                                                                                                                                                                              |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | port_id               | String                | Specifies the ID for identifying the backend resource of the VPC endpoint service. The ID is in UUID format. The values are as follows:                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  If the backend resource is a load balancer, the value is the ID of the port bound to the private IP address of the load balancer.                                                                                                                                              |
      |                       |                       | -  If the backend resource is an ECS, the value is the NIC ID of the ECS where the VPC endpoint service is deployed.                                                                                                                                                              |
      |                       |                       | -  If the backend resource is a virtual IP address, the value is the port ID of the physical server where virtual resources are created. (This value will be discarded. The LB type is recommended.)                                                                              |
      |                       |                       | -  If the backend resource is a BMS, the value is the NIC ID of the BMS where the VPC endpoint service is deployed. (This value will be discarded. The LB type is recommended.)                                                                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | pool_id               | String                | Specifies the ID of the cluster associated with the target VPCEP resource.                                                                                                                                                                                                        |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_name          | String                | Specifies the name of the VPC endpoint service.                                                                                                                                                                                                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | server_type           | String                | Specifies the resource type.                                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **LB**: indicates a load balancer.                                                                                                                                                                                                                                             |
      |                       |                       | -  **VM**: indicates an ECS.                                                                                                                                                                                                                                                      |
      |                       |                       | -  **VIP**: indicates a virtual IP address. (This value has been discarded. The LB type is recommended.)                                                                                                                                                                          |
      |                       |                       | -  **BMS**: indicates a BMS. (This value has been discarded. The LB type is recommended.)                                                                                                                                                                                         |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | vpc_id                | String                | Specifies the ID of the VPC to which the backend resource of the VPC endpoint service belongs.                                                                                                                                                                                    |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | approval_enabled      | Boolean               | Specifies whether connection approval is required.                                                                                                                                                                                                                                |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **false**: Connection approval is not required. The created VPC endpoint is in the **accepted** state.                                                                                                                                                                         |
      |                       |                       | -  **true**: Connection approval is required. The created VPC endpoint is in the **pendingAcceptance** state until the owner of the associated VPC endpoint service approves the connection.                                                                                      |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the status of the VPC endpoint service.                                                                                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **creating**: The VPC endpoint service is being created.                                                                                                                                                                                                                       |
      |                       |                       | -  **available**: The VPC endpoint service is connectable.                                                                                                                                                                                                                        |
      |                       |                       | -  **failed**: The VPC endpoint service failed to be created.                                                                                                                                                                                                                     |
      |                       |                       | -  **deleting**: The VPC endpoint service is being deleted.                                                                                                                                                                                                                       |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_type          | String                | Specifies the type of the VPC endpoint service.                                                                                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | There are two types of VPC endpoint services: interface and gateway.                                                                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  Gateway: VPC endpoint services of this type are configured by O&M personnel. You can use them directly without the need to create one by yourselves.                                                                                                                           |
      |                       |                       | -  Interface: VPC endpoint services of this type include cloud services configured by O&M personnel and private services created by yourselves. You cannot configure these cloud services, but can use them.                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | You can perform the operations in :ref:`Creating a VPC Endpoint <vpcep_06_0303>` to create VPC endpoints for accessing VPC endpoints of the gateway and interface types.                                                                                                          |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint service.                                                                                                                                                                                                                          |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the update time of the VPC endpoint service.                                                                                                                                                                                                                            |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | project_id            | String                | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`.                                                                                                                                                      |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ports                 | Array of objects      | Lists the port mappings opened to the VPC endpoint service. For details, see :ref:`Table 3 <vpcep_06_0202__table22278337>`.                                                                                                                                                       |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | Duplicate port mappings are not allowed in the same VPC endpoint service. If multiple VPC endpoint services share the same **port_id** value, either **server_port** or **protocol**, or both **server_port** and **protocol** of each of these endpoint services must be unique. |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tcp_proxy             | String                | Specifies whether the client IP address and port number or **marker_id** information is transmitted to the server. The following methods are supported:                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  TCP TOA: The client information is inserted into field **tcp option** and transmitted to the server.                                                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       |    .. note::                                                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       |       TCP TOA is supported only when the backend resource is OBS.                                                                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  Proxy Protocol: The client information is inserted into field **tcp payload** and transmitted to the server.                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | This parameter is available only when the server can parse fields **tcp option** and **tcp payload**.                                                                                                                                                                             |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | The values are as follows:                                                                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **close**: The TOA and Proxy Protocol methods are neither used.                                                                                                                                                                                                                |
      |                       |                       | -  **toa_open**: The TOA method is used.                                                                                                                                                                                                                                          |
      |                       |                       | -  **proxy_open**: The Proxy Protocol method is used.                                                                                                                                                                                                                             |
      |                       |                       | -  **open**: The TOA and Proxy Protocol methods are both used.                                                                                                                                                                                                                    |
      |                       |                       | -  **proxy_vni**: The TOA Protocol method is not used. Proxy and virtual network ID are used.                                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | The default value is **close**.                                                                                                                                                                                                                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tags                  | Array of objects      | Lists the resource tags. For details, see :ref:`Table 4 <vpcep_06_0202__table489217571060>`.                                                                                                                                                                                      |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | error                 | Array of objects      | Specifies the error message.                                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | This field is returned when the status of the VPC endpoint service changes to **failed**. For details, see :ref:`Table 5 <vpcep_06_0202__table8651145512302>`.                                                                                                                    |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | description           | String                | Supplementary information about the VPC endpoint service.                                                                                                                                                                                                                         |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0202__table22278337:

   .. table:: **Table 3** Port parameters

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                     |
      +=======================+=======================+=================================================================================================================================+
      | client_port           | Integer               | Specifies the port for accessing the VPC endpoint.                                                                              |
      |                       |                       |                                                                                                                                 |
      |                       |                       | This port is provided by the VPC endpoint, allowing you to access the VPC endpoint service. Supported range: **1** to **65535** |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
      | server_port           | Integer               | Specifies the port for accessing the VPC endpoint service.                                                                      |
      |                       |                       |                                                                                                                                 |
      |                       |                       | This port is provided by the backend service to provide services. Supported range: **1** to **65535**                           |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
      | protocol              | String                | Specifies the port mapping protocol. TCP is supported.                                                                          |
      |                       |                       |                                                                                                                                 |
      |                       |                       | The default value is **TCP**.                                                                                                   |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0202__table489217571060:

   .. table:: **Table 4** Tags parameters

      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                                      |
      +===========+========+==================================================================================================================================================================================================+
      | key       | String | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters. **key** cannot be left blank. It can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the tag value. A tag value contains a maximum of 43 Unicode characters and can be left blank. It can contain only digits, letters, hyphens (-), underscores (_), and at signs (@).     |
      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0202__table8651145512302:

   .. table:: **Table 5** Error parameters

      ============= ====== ============================
      Parameter     Type   Description
      ============= ====== ============================
      error_code    String Specifies the error code.
      error_message String Specifies the error message.
      ============= ====== ============================

-  Example response

   .. code-block::

      {
          "id":"4189d3c2-8882-4871-a3c2-d380272eed83",
          "port_id":"4189d3c2-8882-4871-a3c2-d380272eed88",
          "vpc_id":"4189d3c2-8882-4871-a3c2-d380272eed80",
          "pool_id":"5289d3c2-8882-4871-a3c2-d380272eed80",
          "status":"available",
          "approval_enabled":false,
          "service_name":"test123",
          "service_type":"interface",
          "server_type":"VM",
          "project_id":"6e9dfd51d1124e8d8498dce894923a0d",
          "description": "",
          "created_at":"2018-01-30T07:42:01Z",
          "ports":
                    [
                      {
                          "client_port":8080,
                          "server_port":90,
                          "protocol":"TCP"
                      },
                      {
                          "client_port":8081,
                          "server_port":80,
                          "protocol":"TCP"
                      }
                    ]
      }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
