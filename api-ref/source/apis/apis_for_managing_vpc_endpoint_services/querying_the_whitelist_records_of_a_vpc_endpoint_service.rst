:original_name: vpcep_06_0208.html

.. _vpcep_06_0208:

Querying the Whitelist Records of a VPC Endpoint Service
========================================================

Function
--------

This API is used to query the whitelist records of a VPC endpoint service.

.. note::

   Your domain ID is in the whitelist of your own VPC endpoint service by default.

URI
---

GET /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}/permissions?permission={permission}&sort_dir={sort_dir}&limit={limit}&offset={offset}

:ref:`Table 1 <vpcep_06_0208__table26447764>` describes the required parameters.

.. _vpcep_06_0208__table26447764:

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
      | permission      | No              | String          | Specifies the authorized domain ID. The format is the **iam:domain::**\ *domain_id*.                                                                         |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | *domain_id* indicates the domain ID, for example, iam:domain::6e9dfd51d1124e8d8498dce894923a0d                                                               |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | Fuzzy search is supported.                                                                                                                                   |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit           | No              | Integer         | Specifies the maximum number of whitelist records displayed on each page.                                                                                    |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | The value ranges from **0** to **500** and is generally **10**, **20**, or **50**. The default value is **10**.                                              |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset          | No              | Integer         | Specifies the offset.                                                                                                                                        |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | All VPC endpoint services after this offset will be queried. The offset must be an integer greater than 0 but less than the number of VPC endpoint services. |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_key        | No              | String          | Specifies the basis for sequencing whitelist records. The value is **create_at**, indicating the time of adding each whitelist record.                       |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | sort_dir        | No              | String          | Specifies the sorting method of the whitelist record list. The value can be:                                                                                 |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | -  **desc**: indicates that whitelist records are sorted in the descending order.                                                                            |
      |                 |                 |                 | -  **asc**: indicates that whitelist records are sorted in the ascending order.                                                                              |
      |                 |                 |                 |                                                                                                                                                              |
      |                 |                 |                 | The default method is **desc**.                                                                                                                              |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   This request is to query whitelist records of the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88/permissions

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Type             | Description                                                                                                                       |
      +=============+==================+===================================================================================================================================+
      | permissions | Array of objects | Lists the whitelist records. For details, see :ref:`Table 4 <vpcep_06_0208__table50257079>`.                                      |
      +-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | total_count | Integer          | Specifies the total number of whitelist records that meet the search criteria. The number is not affected by the limit or offset. |
      +-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0208__table50257079:

   .. table:: **Table 4** Whitelist record parameters

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the permission.                                                                                                                                                                                          |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | permission            | String                | Lists the whitelist records.                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                                     |
      |                       |                       | The permission format is **iam:domain:: 6e9dfd51d1124e8d8498dce894923a0d** or **\***. **\*** indicates all users can connect to the VPC endpoint service. **6e9dfd51d1124e8d8498dce894923a0d** indicates the domain ID of the user. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | **create_at**: indicates the time of adding the whitelist record.                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                     |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                                                                                                  |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "permissions":
         [
                {
                      "id":"f2659906-c622-480a-83e9-ef42bdb67b90",
                      "permission":"*",
                      "created_at":"2018-10-18T13:26:40Z"
                  }
          ],
       "total_count":1
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
