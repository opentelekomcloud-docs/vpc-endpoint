:original_name: vpcep_06_0205.html

.. _vpcep_06_0205:

Querying VPC Endpoint Services
==============================

Function
--------

This API is used to query VPC endpoint services.

URI
---

GET /v1/{project_id}/vpc-endpoint-services?endpoint_service_name={endpoint_service_name}&id={id}&sort_key={sort_key}&sort_dir={sort_dir}&limit={limit}&offset={offset}&status={status}

:ref:`Table 1 <vpcep_06_0205__table29895862>` describes the parameter in this URI.

.. _vpcep_06_0205__table29895862:

.. table:: **Table 1** URI parameter

   +------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Description                                                                                                                  |
   +============+===========+==============================================================================================================================+
   | project_id | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +------------+-----------+------------------------------------------------------------------------------------------------------------------------------+

.. _vpcep_06_0205__table5645742:

.. table:: **Table 2** Query parameters

   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory       | Type            | Description                                                                                                                                                  |
   +=======================+=================+=================+==============================================================================================================================================================+
   | endpoint_service_name | No              | String          | Specifies the name of the VPC endpoint service. The name is not case-sensitive and supports fuzzy match.                                                     |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                    | No              | String          | Specifies the unique ID of the VPC endpoint service.                                                                                                         |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | No              | String          | Specifies the status of the VPC endpoint service.                                                                                                            |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | -  **creating**: The VPC endpoint service is being created.                                                                                                  |
   |                       |                 |                 | -  **available**: The VPC endpoint service is connectable.                                                                                                   |
   |                       |                 |                 | -  **failed**: The VPC endpoint service failed to be created.                                                                                                |
   |                       |                 |                 | -  **deleting**: The VPC endpoint service is being deleted.                                                                                                  |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_key              | No              | String          | Specifies the sorting field of the VPC endpoint service list. The field can be:                                                                              |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | -  **created_at**: VPC endpoint services are sorted by creation time.                                                                                        |
   |                       |                 |                 | -  **updated_at**: VPC endpoint services are sorted by update time.                                                                                          |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | The default field is **created_at**.                                                                                                                         |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_dir              | No              | String          | Specifies the sorting method of the VPC endpoint service list. The method can be:                                                                            |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | -  **desc**: VPC endpoint services are sorted in descending order.                                                                                           |
   |                       |                 |                 | -  **asc**: VPC endpoint services are sorted in ascending order.                                                                                             |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | The default method is **desc**.                                                                                                                              |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit                 | No              | Integer         | Specifies the maximum number of VPC endpoint services displayed on each page.                                                                                |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | The number ranges from **0** to **1000** and is generally **10**, **20**, or **50**. The default number is **10**.                                           |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset                | No              | Integer         | Specifies the offset.                                                                                                                                        |
   |                       |                 |                 |                                                                                                                                                              |
   |                       |                 |                 | All VPC endpoint services after this offset will be queried. The offset must be an integer greater than 0 but less than the number of VPC endpoint services. |
   +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  .. _vpcep_06_0205__li1385457113510:

   Parameter description

   None

-  Example request

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services

Response
--------

-  Parameter description

   .. _vpcep_06_0205__table50811679:

   .. table:: **Table 3** Response parameters

      +-------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter         | Type             | Description                                                                                                                           |
      +===================+==================+=======================================================================================================================================+
      | endpoint_services | Array of objects | Lists the VPC endpoint services. For details, see :ref:`Table 4 <vpcep_06_0205__table11315049>`.                                      |
      +-------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------+
      | total_count       | Integer          | Specifies the total number of VPC endpoint services that meet the search criteria. The number is not affected by the limit or offset. |
      +-------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0205__table11315049:

   .. table:: **Table 4** endpoint_service parameters

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
      | domain_id             | String                | Specifies the user's domain ID.                                                                                                                                                                                                                                                   |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ports                 | Array of objects      | Lists the port mappings opened to the VPC endpoint service. For details, see :ref:`Table 5 <vpcep_06_0205__table31283788>`.                                                                                                                                                       |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | Duplicate port mappings are not allowed in the same VPC endpoint service. If multiple VPC endpoint services share the same **port_id** value, either **server_port** or **protocol**, or both **server_port** and **protocol** of each of these endpoint services must be unique. |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tags                  | Array of objects      | Lists the resource tags. For details, see :ref:`Table 6 <vpcep_06_0205__table489217571060>`.                                                                                                                                                                                      |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | connection_count      | Integer               | Specifies the number of **Creating** or **Accepted** VPC endpoints under the VPC endpoint service.                                                                                                                                                                                |
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
      | error                 | Array of objects      | Specifies the error message.                                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                                   |
      |                       |                       | This field is returned when the status of the VPC endpoint service changes to **failed**. For details, see :ref:`Table 7 <vpcep_06_0205__table178701348456>`.                                                                                                                     |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | pool_id               | String                | Specifies the ID of the cluster the VPC endpoint belongs to.                                                                                                                                                                                                                      |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | description           | String                | Supplementary information about the VPC endpoint service.                                                                                                                                                                                                                         |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0205__table31283788:

   .. table:: **Table 5** Port parameters

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

   .. _vpcep_06_0205__table489217571060:

   .. table:: **Table 6** Tags parameters

      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                                      |
      +===========+========+==================================================================================================================================================================================================+
      | key       | String | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters. **key** cannot be left blank. It can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the tag value. A tag value contains a maximum of 43 Unicode characters and can be left blank. It can contain only digits, letters, hyphens (-), underscores (_), and at signs (@).     |
      +-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0205__table178701348456:

   .. table:: **Table 7** Error parameters

      ============= ====== ============================
      Parameter     Type   Description
      ============= ====== ============================
      error_code    String Specifies the error code.
      error_message String Specifies the error message.
      ============= ====== ============================

-  .. _vpcep_06_0205__li64495211:

   Example response

   .. code-block::

      {
         "endpoint_services":[
               {
                 "id":"4189d3c2-8882-4871-a3c2-d380272eed83",
                 "port_id":"4189d3c2-8882-4871-a3c2-d380272eed88",
                 "vpc_id":"4189d3c2-8882-4871-a3c2-d380272eed80",
                 "status":"available",
                 "approval_enabled":false,
                 "service_name":"test123",
                 "server_type":"VM",
                 "service_type":"interface",
                 "ports":[
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
                   ],
                 "project_id":"6e9dfd51d1124e8d8498dce894923a0d",
                 "domain_id" : "5fc973eea581490997e82ea11a1df31f",
                 "description": "",
                 "created_at":"2018-01-30T07:42:01Z",
                 "updated_at":"2018-01-30T07:42:01Z"
               }
           ],
         "total_count":1
      }
