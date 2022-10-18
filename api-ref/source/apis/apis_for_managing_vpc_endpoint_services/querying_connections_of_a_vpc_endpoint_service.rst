:original_name: vpcep_06_0206.html

.. _vpcep_06_0206:

Querying Connections of a VPC Endpoint Service
==============================================

Function
--------

This API is used to query connections of a VPC endpoint service. The marker ID is the unique ID of each connection.

URI
---

GET /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}/connections?id={vpc_endpoint_id}&marker_id={marker_id}&status={status}&sort_key={sort_key}&sort_dir={sort_dir}&limit={limit}&offset={offset}

:ref:`Table 1 <vpcep_06_0206__table36274863>` describes the required parameters.

.. _vpcep_06_0206__table36274863:

.. table:: **Table 1** Parameters

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

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                  |
      +=================+=================+=================+==============================================================================================================================================================+
      | id              | No              | String          | Specifies the unique ID of the VPC endpoint.                                                                                                                 |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | marker_id       | No              | String          | Specifies the packet ID of the VPC endpoint.                                                                                                                 |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status          | No              | String          | Specifies the connection status of the VPC endpoint.                                                                                                         |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | -  **pendingAcceptance**: indicates that the VPC endpoint is pending acceptance.                                                                             |
      |                 |                 |                 | -  **accepted**: indicates the VPC endpoint has been accepted.                                                                                               |
      |                 |                 |                 | -  **rejected**: indicates the VPC endpoint has been rejected.                                                                                               |
      |                 |                 |                 | -  **failed**: indicates the creation of the VPC endpoint failed.                                                                                            |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_key        | No              | String          | Specifies the basis for sequencing VPC endpoint services. The value can be:                                                                                  |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | -  **create_at**: indicates the creation time of the VPC endpoint.                                                                                           |
      |                 |                 |                 | -  **update_at**: indicates the update time of the VPC endpoint.                                                                                             |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | The default field is **create_at**.                                                                                                                          |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_dir        | No              | String          | Specifies the sorting method of the VPC endpoint list. The value can be:                                                                                     |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | -  **desc**: indicates that VPC endpoints are sorted in the descending order.                                                                                |
      |                 |                 |                 | -  **asc**: indicates that VPC endpoints are sorted in the ascending order.                                                                                  |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | The default method is **desc**.                                                                                                                              |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit           | No              | Integer         | Specifies the maximum number of connections displayed on each page.                                                                                          |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | The value ranges from **0** to **1000** and is generally **10**, **20**, or **50**. The default value is **10**.                                             |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset          | No              | Integer         | Specifies the offset.                                                                                                                                        |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | All VPC endpoint services after this offset will be queried. The offset must be an integer greater than 0 but less than the number of VPC endpoint services. |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   This request is to query connections of the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88/connections

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-------------+------------------+-------------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Type             | Description                                                                                                                   |
      +=============+==================+===============================================================================================================================+
      | connections | Array of objects | Lists the connections. For details, see :ref:`Table 4 <vpcep_06_0206__table35346078>`.                                        |
      +-------------+------------------+-------------------------------------------------------------------------------------------------------------------------------+
      | total_count | Integer          | Specifies the total number of VPC endpoints that meet the search criteria. The number is not affected by the limit or offset. |
      +-------------+------------------+-------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0206__table35346078:

   .. table:: **Table 4** Connection parameters

      +-----------------------+-----------------------+----------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                      |
      +=======================+=======================+==================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint.                                     |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------+
      | marker_id             | Integer               | Specifies the packet ID of the VPC endpoint.                                     |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint.                                 |
      |                       |                       |                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                               |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the update time of the VPC endpoint.                                   |
      |                       |                       |                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                               |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------+
      | domain_id             | String                | Specifies the user's domain ID.                                                  |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------+
      | status                | String                | Specifies the connection status of the VPC endpoint.                             |
      |                       |                       |                                                                                  |
      |                       |                       | -  **pendingAcceptance**: indicates that the VPC endpoint is pending acceptance. |
      |                       |                       | -  **creating**: indicates the VPC endpoint is being created.                    |
      |                       |                       | -  **accepted**: indicates the VPC endpoint has been accepted.                   |
      |                       |                       | -  **rejected**: indicates the VPC endpoint has been rejected.                   |
      |                       |                       | -  **failed**: indicates the creation of the VPC endpoint failed.                |
      |                       |                       | -  **deleting**: indicates the VPC endpoint is being deleted.                    |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "connections": [
          {
            "id": "adb7b229-bb11-4072-bcc0-3327cd784263",
            "status": "accepted",
            "marker_id": 16777510,
            "domain_id": "5fc973eea581490997e82ea11a1df31f",
            "created_at": "2018-09-17T11:10:11Z",
            "updated_at": "2018-09-17T11:10:12Z"
          },
          {
            "id": "fd69d29f-dc29-4a9b-80d8-b51d1e7e58ea",
            "status": "accepted",
            "marker_id": 16777513,
            "domain_id": "5fc973eea581490997e82ea11a1df31f",
            "created_at": "2018-09-17T07:28:56Z",
            "updated_at": "2018-09-17T07:28:58Z"
          }
        ],
        "total_count":2
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
