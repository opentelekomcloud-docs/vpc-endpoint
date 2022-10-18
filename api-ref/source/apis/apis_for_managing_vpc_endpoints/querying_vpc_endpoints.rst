:original_name: vpcep_06_0306.html

.. _vpcep_06_0306:

Querying VPC Endpoints
======================

Function
--------

This API is used to query VPC endpoints.

URI
---

GET /v1/{project_id}/vpc-endpoints?endpoint_service_name={endpoint_service_name}&vpc_id={vpc_id}&limit={limit}&offset={offset}&id={id}&sort_key={sort_key}&sort_dir={sort_dir}

:ref:`Table 1 <vpcep_06_0306__table35342882>` describes the required parameters.

.. _vpcep_06_0306__table35342882:

.. table:: **Table 1** Parameter description

   +------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Description                                                                                                                    |
   +============+===========+================================================================================================================================+
   | project_id | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003_0>`. |
   +------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   .. table:: **Table 2** Request parameters

      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory       | Type            | Description                                                                                                                                                  |
      +=======================+=================+=================+==============================================================================================================================================================+
      | endpoint_service_name | No              | String          | Specifies the name of the VPC endpoint service. The name is not case-sensitive and supports fuzzy match.                                                     |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | vpc_id                | No              | String          | Specifies the ID of the VPC where the VPC endpoint is to be created.                                                                                         |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | id                    | No              | String          | Specifies the unique ID of the VPC endpoint.                                                                                                                 |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit                 | No              | Integer         | Specifies the maximum number of VPC endpoints displayed on each page.                                                                                        |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | The number ranges from **0** to **1000** and is generally **10**, **20**, or **50**. The default number is **10**.                                           |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset                | No              | Integer         | Specifies the offset.                                                                                                                                        |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | All VPC endpoint services after this offset will be queried. The offset must be an integer greater than 0 but less than the number of VPC endpoint services. |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_key              | No              | String          | Specifies the sorting field of the VPC endpoint list. The field can be:                                                                                      |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | -  **create_at**: indicates that VPC endpoints are sorted by creation time.                                                                                  |
      |                       |                 |                 | -  **update_at**: indicates that VPC endpoints are sorted by update time.                                                                                    |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | The default field is **create_at**.                                                                                                                          |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_dir              | No              | String          | Specifies the sorting method of the VPC endpoint list. The method can be:                                                                                    |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | -  **desc**: indicates that VPC endpoints are sorted in the descending order.                                                                                |
      |                       |                 |                 | -  **asc**: indicates that VPC endpoints are sorted in the ascending order.                                                                                  |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | The default method is **desc**.                                                                                                                              |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoints

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-------------+------------------+-------------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Type             | Description                                                                                                                   |
      +=============+==================+===============================================================================================================================+
      | endpoints   | Array of objects | Lists the VPC endpoints. For details, see :ref:`Table 4 <vpcep_06_0306__table66917326>`.                                      |
      +-------------+------------------+-------------------------------------------------------------------------------------------------------------------------------+
      | total_count | Integer          | Specifies the total number of VPC endpoints that meet the search criteria. The number is not affected by the limit or offset. |
      +-------------+------------------+-------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0306__table66917326:

   .. table:: **Table 4** VPC endpoint parameters

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint.                                                                                                                                                                     |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_type          | String                | Specifies the type of the VPC endpoint service that is associated with the VPC endpoint.                                                                                                                         |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  Gateway: VPC endpoint services of this type are configured by operations people. You can use them directly without the need to create one by yourselves.                                                      |
      |                       |                       | -  Interface: VPC endpoint services of this type include cloud services configured by operations people and private services created by yourselves. You cannot configure these cloud services, but can use them. |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | You can perform the operations in :ref:`Creating a VPC Endpoint <vpcep_06_0303>` to create VPC endpoints for accessing VPC endpoints of the gateway and interface types.                                         |
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
      | tags                  | Array of objects      | Lists the resource tags. For details, see :ref:`Table 5 <vpcep_06_0306__table489217571060>`.                                                                                                                     |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | error                 | Array of objects      | Specifies the error message.                                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | This field is returned when the status of the VPC endpoint changes to **failed**. For details, see :ref:`Table 6 <vpcep_06_0306__table1736562411812>`.                                                           |
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

   .. _vpcep_06_0306__table489217571060:

   .. table:: **Table 5** **ResourceTags** parameters

      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                               |
      +===========+========+===========================================================================================================================================================================================+
      | key       | String | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters. This parameter cannot be left blank. It can contain only digits, letters, hyphens (-), and underscores (_). |
      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the tag value. A tag value contains a maximum of 43 Unicode characters and can be left blank. It can contain only digits, letters, hyphens (-), and underscores (_).            |
      +-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0306__table1736562411812:

   .. table:: **Table 6** Error parameters

      ============= ====== ============================
      Parameter     Type   Description
      ============= ====== ============================
      error_code    String Specifies the error code.
      error_message String Specifies the error message.
      ============= ====== ============================

-  Example response

   .. code-block::

      {
      "endpoints":
       [
          {
            "id":"03184a04-95d5-4555-86c4-e767a371ff99",
            "status":"accepted",
            "ip":"192.168.0.232",
            "marker_id":16777337,
            "active_status":"active",
            "vpc_id":"84758cf5-9c62-43ae-a778-3dbd8370c0a4",
            "service_type":"interface",
            "project_id":"295dacf46a4842fcbf7844dc2dc2489d",
            "subnet_id":"68bfbcc1-dff2-47e4-a9d4-332b9bc1b8de",
            "enable_dns":"true",
            "dns_name":"test123",
            "created_at":"2018-10-18T06:49:46Z",
            "updated_at":"2018-10-18T06:49:50Z",
            "endpoint_service_id":"5133655d-0e28-4090-b669-13f87b355c78",
            "endpoint_service_name":"test123",
            "whitelist":["127.0.0.1"],
            "enable_whitelist":true,
            "tags":
              [
                {
                  "key":"test1",
                  "value":"test1"
                }
              ]
          },
          {
            "id":"43b0e3b0-eec9-49da-866b-6687b75f9fe5",
            "status":"accepted",
            "ip":"192.168.0.115",
            "marker_id":16777322,
            "active_status":"active",
            "vpc_id":"e251b400-2963-4131-b38a-da81e32026ee",
            "service_type":"interface",
            "project_id":"295dacf46a4842fcbf7844dc2dc2489d",
            "subnet_id":"65528a22-59a1-4972-ba64-88984b3207cd",
            "enable_dns":"true",
            "dns_name":"test123",
            "created_at":"2018-10-18T06:36:20Z",
            "updated_at":"2018-10-18T06:36:24Z",
            "endpoint_service_id":"5133655d-0e28-4090-b669-13f87b355c78",
            "endpoint_service_name":"test123",
            "whitelist":["127.0.0.1"],
            "enable_whitelist":true,
            "tags":
              [
                {
                  "key":"test1",
                  "value":"test1"
                }
              ]
          }
       ],
       "total_count":17
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
