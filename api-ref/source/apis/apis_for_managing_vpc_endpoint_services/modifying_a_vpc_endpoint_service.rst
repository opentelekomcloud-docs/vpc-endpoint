:original_name: vpcep_06_0203.html

.. _vpcep_06_0203:

Modifying a VPC Endpoint Service
================================

**Function**
------------

This API is used to modify a VPC endpoint service.

URI
---

PUT /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}

:ref:`Table 1 <vpcep_06_0203__table28352855>` describes the required parameters.

.. _vpcep_06_0203__table28352855:

.. table:: **Table 1** Parameter description

   +-------------------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Mandatory | Description                                                                                                                    |
   +=========================+===========+================================================================================================================================+
   | project_id              | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003_0>`. |
   +-------------------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_service_id | Yes       | Specifies the ID of the VPC endpoint service.                                                                                  |
   +-------------------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   .. table:: **Table 2** Request parameters

      +------------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter        | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                                                                                                         |
      +==================+=================+==================+=====================================================================================================================================================================================================================================================================================================================================================================+
      | approval_enabled | No              | Boolean          | Specifies whether connection approval is required.                                                                                                                                                                                                                                                                                                                  |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                                                                                                     |
      |                  |                 |                  | -  **false**: indicates that connection approval is not required. The created VPC endpoint is in the **Accepted** state.                                                                                                                                                                                                                                            |
      |                  |                 |                  | -  **true**: indicates that connection approval is required. The created VPC endpoint is unavailable until the owner of the associated VPC endpoint service approves the connection.                                                                                                                                                                                |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                                                                                                     |
      |                  |                 |                  | The default value is **true**.                                                                                                                                                                                                                                                                                                                                      |
      +------------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_name     | No              | String           | Specifies the name of the VPC endpoint service. The name can contain a maximum of 16 characters, including letters, digits, underscores (_), and hyphens (-).                                                                                                                                                                                                       |
      +------------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ports            | No              | Array of objects | Lists the port mappings opened to the VPC endpoint service. For details, see :ref:`Table 3 <vpcep_06_0203__table1186184673416>`.                                                                                                                                                                                                                                    |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                                                                                                     |
      |                  |                 |                  | Duplicate port mappings are not allowed in the same VPC endpoint service. If multiple VPC endpoint services share the same **port_id** value, service ports and terminal ports of all these endpoint services cannot be duplicated when the protocol is the same. A maximum of 200 port mappings can be created at a time.                                          |
      +------------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | port_id          | No              | String           | Specifies the ID for identifying the backend resource of the VPC endpoint service. The ID is in the form of the UUID. The values are as follows:                                                                                                                                                                                                                    |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                                                                                                     |
      |                  |                 |                  | -  If the backend resource is an enhanced load balancer, the value is the ID of the port bound to the private IP address of the load balancer. For details, see response field **vip_port_id** in `Querying Details of a Load Balancer <https://docs.otc.t-systems.com/en-us/api/elb/en-us_topic_0141008271.html>`__ in the *Elastic Load Balancing API Reference*. |
      |                  |                 |                  | -  If the backend resource is an ECS, the value is the NIC ID of the ECS where the VPC endpoint service is deployed. For details, see `Querying NICs of an ECS <https://docs.otc.t-systems.com/en-us/api/ecs/en-us_topic_0020212662.html>`__ in the *Elastic Load Balancing API Reference*.                                                                         |
      |                  |                 |                  | -  If the backend resource is a virtual IP address, the value is the NIC ID of the physical server where virtual resources are created.                                                                                                                                                                                                                             |
      +------------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | vip_port_id      | No              | String           | Specifies the ID of the virtual NIC to which the virtual IP address is bound.                                                                                                                                                                                                                                                                                       |
      +------------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0203__table1186184673416:

   .. table:: **Table 3** Port mapping parameters

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                     |
      +=================+=================+=================+=================================================================================================================================+
      | client_port     | No              | Integer         | Specifies the port for accessing the VPC endpoint.                                                                              |
      |                 |                 |                 |                                                                                                                                 |
      |                 |                 |                 | This port is provided by the VPC endpoint, allowing you to access the VPC endpoint service. Supported range: **1** to **65535** |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------+
      | server_port     | No              | Integer         | Specifies the port for accessing the VPC endpoint service.                                                                      |
      |                 |                 |                 |                                                                                                                                 |
      |                 |                 |                 | This port is provided by the backend service to provide services. Supported range: **1** to **65535**                           |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------+
      | protocol        | No              | String          | Specifies the protocol used in port mappings. The protocol can be **TCP** or **UDP**. The default protocol is **TCP**.          |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   This request is to modify the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      PUT https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88

   .. code-block::

      {
         "approval_enabled":true,
         "service_name":"test",
         "ports":[
                   {
                      "client_port":8081,
                      "server_port":22,
                      "protocol":"TCP"
                   },
                   {
                      "client_port":8082,
                      "server_port":23,
                      "protocol":"TCP"
                   }
                 ]
      }

Response
--------

-  Parameter description

   .. table:: **Table 4** Response parameters

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                                                       |
      +=======================+=======================+===================================================================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint service.                                                                                                                                                                                                              |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | port_id               | String                | Specifies the ID for identifying the backend resource of the VPC endpoint service. The ID is in the form of the UUID. The values are as follows:                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  If the backend resource is an enhanced load balancer, the value is the ID of the port bound to the private IP address of the load balancer.                                                                                                                    |
      |                       |                       | -  If the backend resource is an ECS, the value is the NIC ID of the ECS where the VPC endpoint service is deployed.                                                                                                                                              |
      |                       |                       | -  If the backend resource is a virtual IP address, the value is the NIC ID of the physical server where virtual resources are created.                                                                                                                           |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | pool_id               | String                | Specifies the ID of the cluster associated with the target VPCEP resource.                                                                                                                                                                                        |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | vip_port_id           | String                | Specifies the ID of the virtual NIC to which the virtual IP address is bound.                                                                                                                                                                                     |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_name          | String                | Specifies the name of the VPC endpoint service.                                                                                                                                                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | server_type           | String                | Specifies the resource type.                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **VM**: indicates the ECS.                                                                                                                                                                                                                                     |
      |                       |                       | -  **VIP**: indicates the virtual IP address.                                                                                                                                                                                                                     |
      |                       |                       | -  **LB**: indicates the enhanced load balancer.                                                                                                                                                                                                                  |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | vpc_id                | String                | Specifies the ID of the VPC to which the backend resource of the VPC endpoint service belongs.                                                                                                                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | approval_enabled      | Boolean               | Specifies whether connection approval is required.                                                                                                                                                                                                                |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **false**: indicates that connection approval is not required. The created VPC endpoint is in the **Accepted** state.                                                                                                                                          |
      |                       |                       | -  **true**: indicates that connection approval is required. The created VPC endpoint is in the **Pending acceptance** state until the owner of the associated VPC endpoint service approves the connection.                                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the status of the VPC endpoint service.                                                                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | **available**: indicates the VPC endpoint service is connectable.                                                                                                                                                                                                 |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_type          | String                | Specifies the type of the VPC endpoint service.                                                                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | There are two types of VPC endpoint services: interface and gateway.                                                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  Gateway: VPC endpoint services of this type are configured by operations people. You can use them directly without the need to create one by yourselves.                                                                                                       |
      |                       |                       | -  Interface: VPC endpoint services of this type include cloud services configured by operations people and private services created by yourselves. You cannot configure these cloud services, but can use them.                                                  |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | You can perform the operations in :ref:`Creating a VPC Endpoint <vpcep_06_0303>` to create VPC endpoints for accessing VPC endpoints of the gateway and interface types.                                                                                          |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint service.                                                                                                                                                                                                          |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                                                                                |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the update time of the VPC endpoint service.                                                                                                                                                                                                            |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                                                                                |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | project_id            | String                | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003_0>`.                                                                                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | cidr_type             | String                | Specifies the network segment type. The type can be **public** or **internal**.                                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **public**: indicates the public subnet CIDR block.                                                                                                                                                                                                            |
      |                       |                       | -  **internal**: indicates the private subnet CIDR block.                                                                                                                                                                                                         |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | The default value is **internal**.                                                                                                                                                                                                                                |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ports                 | Array of objects      | Lists the port mappings opened to the VPC endpoint service. For details, see :ref:`Table 5 <vpcep_06_0203__table20064649>`.                                                                                                                                       |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | Duplicate port mappings are not allowed in the same VPC endpoint service. If multiple VPC endpoint services share the same **port_id** value, service ports and terminal ports of all these endpoint services cannot be duplicated when the protocol is the same. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tcp_proxy             | String                | Specifies whether the client IP address and port number or **marker_id** information is transmitted to the server. The following methods are supported:                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  TCP TOA: The client information is inserted into field **tcp option** and transmitted to the server.                                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       |    .. note::                                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       |       TCP TOA is supported only when the backend resource is OBS.                                                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  Proxy Protocol: The client information is inserted into field **tcp payload** and transmitted to the server.                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | This parameter is available only when the server can parse fields **tcp option** and **tcp payload**.                                                                                                                                                             |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | The values are as follows:                                                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | -  **close**: indicates that the TOA and Proxy Protocol methods are neither used.                                                                                                                                                                                 |
      |                       |                       | -  **toa_open**: indicates that the TOA method is used.                                                                                                                                                                                                           |
      |                       |                       | -  **proxy_open**: indicates that the Proxy Protocol method is used.                                                                                                                                                                                              |
      |                       |                       | -  **open**: indicates that the TOA and Proxy Protocol methods are both used.                                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                                                                   |
      |                       |                       | The default value is **close**.                                                                                                                                                                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tags                  | Array of objects      | Lists the resource tags. For details, see :ref:`Table 6 <vpcep_06_0203__table489217571060>`.                                                                                                                                                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0203__table20064649:

   .. table:: **Table 5** Port mapping parameters

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
      | protocol              | String                | Specifies the protocol used in port mappings. The protocol can be **TCP**\ or **UDP**. The default protocol is **TCP**.         |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0203__table489217571060:

   .. table:: **Table 6** **ResourceTags** parameters

      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                               |
      +===========+========+===========================================================================================================================================================================================+
      | key       | String | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters. This parameter cannot be left blank. It can contain only digits, letters, hyphens (-), and underscores (_). |
      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the tag value. A tag value contains a maximum of 43 Unicode characters and can be left blank. It can contain only digits, letters, hyphens (-), and underscores (_).            |
      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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
          "created_at":"2018-01-30T07:42:01.174",
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

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
