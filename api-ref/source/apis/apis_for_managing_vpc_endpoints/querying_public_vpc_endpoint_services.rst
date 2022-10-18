:original_name: vpcep_06_0301.html

.. _vpcep_06_0301:

Querying Public VPC Endpoint Services
=====================================

Function
--------

This API is used to query public VPC endpoint services. These services are created by operations people and can be visible to and assessed by all users.

URI
---

GET /v1/{project_id}/vpc-endpoint-services/public?limit={limit}&offset={offset}&endpoint_service_name={endpoint_service_name}&id={endpoint_service_id}&sort_key={sort_key}&sort_dir={sort_dir}

:ref:`Table 1 <vpcep_06_0301__table52235709>` describes the required parameters.

.. _vpcep_06_0301__table52235709:

.. table:: **Table 1** Parameters

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
      | limit                 | No              | Integer         | Specifies the maximum number of public VPC endpoint services displayed on each page.                                                                         |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | The value ranges from **0** to **1000** and is generally **10**, **20**, or **50**. The default value is **10**.                                             |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset                | No              | Integer         | Specifies the offset.                                                                                                                                        |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | All VPC endpoint services after this offset will be queried. The offset must be an integer greater than 0 but less than the number of VPC endpoint services. |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | endpoint_service_name | No              | String          | Specifies the name of the public VPC endpoint service. The value is not case-sensitive and supports fuzzy match.                                             |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | id                    | No              | String          | Specifies the unique ID of the public VPC endpoint service.                                                                                                  |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_key              | No              | String          | Specifies the sorting field of the VPC endpoint service list. The field can be:                                                                              |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | -  **create_at**: indicates that VPC endpoint services are sorted by creation time.                                                                          |
      |                       |                 |                 | -  **update_at**: indicates that VPC endpoint services are sorted by update time.                                                                            |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | The default field is **create_at**.                                                                                                                          |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_dir              | No              | String          | Specifies the sorting method of the VPC endpoint service list. The method can be:                                                                            |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | -  **desc**: indicates that VPC endpoint services are sorted in the descending order.                                                                        |
      |                       |                 |                 | -  **asc**: indicates that VPC endpoint services are sorted in the ascending order.                                                                          |
      |                       |                 |                 |                                                                                                                                                              |
      |                       |                 |                 | The default method is **desc**.                                                                                                                              |
      +-----------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services/public

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-------------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter         | Type             | Description                                                                                                                                  |
      +===================+==================+==============================================================================================================================================+
      | endpoint_services | Array of objects | Lists the VPC endpoint services. For details, see :ref:`Table 4 <vpcep_06_0301__table55935485>`.                                             |
      +-------------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
      | total_count       | Integer          | Specifies the total number of public VPC endpoint services that meet the search criteria. The number is not affected by the limit or offset. |
      +-------------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0301__table55935485:

   .. table:: **Table 4** **endpoint_service** parameters

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the public VPC endpoint service.                                                                                                                                                      |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | owner                 | String                | Specifies the owner of the VPC endpoint service.                                                                                                                                                                 |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_name          | String                | Specifies the name of the public VPC endpoint service.                                                                                                                                                           |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_type          | String                | Specifies the type of the VPC endpoint service. The value can be:                                                                                                                                                |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  Gateway: VPC endpoint services of this type are configured by operations people. You can use them directly without the need to create one by yourselves.                                                      |
      |                       |                       | -  Interface: VPC endpoint services of this type include cloud services configured by operations people and private services created by yourselves. You cannot configure these cloud services, but can use them. |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | You can perform the operations in :ref:`Creating a VPC Endpoint <vpcep_06_0303>` to create VPC endpoints for accessing VPC endpoints of the gateway and interface types.                                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint service.                                                                                                                                                         |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                               |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | is_charge             | Boolean               | Specifies whether the associated VPC endpoint carries a charge.                                                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                  |
      |                       |                       | -  **true**: indicates that the associated VPC endpoint carries a charge.                                                                                                                                        |
      |                       |                       | -  **false**: indicates that the associated VPC endpoint does not a charge.                                                                                                                                      |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "endpoint_services": [
          {
            "id": "b0e22f6f-26f4-461c-b140-d873464d4fa0",
            "owner": "example"
            "service_name": "test123",
            "service_type": "interface",
            "created_at": "2018-09-10T13:13:23Z",
            "is_charge": "true"
          },
          {
            "id": "26391a76-546b-42a9-b2fc-496ec68c0e4d",
            "owner": "example"
            "service_name":  "OBS",
            "service_type": "gateway",
            "created_at": "2019-03-28T09:30:27Z",
            "is_charge": "true"
          }
        ],
        "total_count": 2
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
