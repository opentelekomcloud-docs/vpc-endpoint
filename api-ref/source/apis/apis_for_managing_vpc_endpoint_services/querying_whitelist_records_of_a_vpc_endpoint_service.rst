:original_name: vpcep_06_0208.html

.. _vpcep_06_0208:

Querying Whitelist Records of a VPC Endpoint Service
====================================================

Function
--------

This API is used to query whitelist records of a VPC endpoint service.

.. note::

   Your account ID is in the whitelist of your own VPC endpoint service by default.

.. _vpcep_06_0208__section13022395:

URI
---

GET /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}/permissions?permission={permission}&sort_key={sort_key}&sort_dir={sort_dir}&limit={limit}&offset={offset}

:ref:`Table 1 <vpcep_06_0208__table26447764>` describes parameters in this URI.

.. _vpcep_06_0208__table26447764:

.. table:: **Table 1** URI parameters

   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Mandatory | Description                                                                                                                  |
   +=========================+===========+==============================================================================================================================+
   | project_id              | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_service_id | Yes       | Specifies the ID of the VPC endpoint service.                                                                                |
   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+

.. _vpcep_06_0208__table61894122:

.. table:: **Table 2** Query parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                  |
   +=================+=================+=================+==============================================================================================================================================================+
   | permission      | No              | String          | Specifies the authorized account ID. The format is the **iam:domain::**\ *domain_id*.                                                                        |
   |                 |                 |                 |                                                                                                                                                              |
   |                 |                 |                 | *domain_id* indicates the account ID, for example, iam:domain::6e9dfd51d1124e8d8498dce894923a0d.                                                             |
   |                 |                 |                 |                                                                                                                                                              |
   |                 |                 |                 | Fuzzy search is supported.                                                                                                                                   |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | Integer         | Specifies the maximum number of whitelist records displayed on each page.                                                                                    |
   |                 |                 |                 |                                                                                                                                                              |
   |                 |                 |                 | The number ranges from **0** to **500** and is generally **10**, **20**, or **50**. The default number is **10**.                                            |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | Integer         | Specifies the offset.                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                              |
   |                 |                 |                 | All VPC endpoint services after this offset will be queried. The offset must be an integer greater than 0 but less than the number of VPC endpoint services. |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_key        | No              | String          | Specifies the sorting field of the whitelist records. The value is **created_at**, indicating that the whitelist records are sorted by creation time.        |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_dir        | No              | String          | Specifies the sorting method of the whitelist record list. The value can be:                                                                                 |
   |                 |                 |                 |                                                                                                                                                              |
   |                 |                 |                 | -  **desc**: Whitelist records are sorted in descending order.                                                                                               |
   |                 |                 |                 | -  **asc**: Whitelist records are sorted in ascending order.                                                                                                 |
   |                 |                 |                 |                                                                                                                                                              |
   |                 |                 |                 | The default method is **desc**.                                                                                                                              |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  Example request

   This request is to query whitelist records of the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88/permissions

Response
--------

-  Parameter description

   .. _vpcep_06_0208__table20176194:

   .. table:: **Table 3** Response parameters

      +-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Type             | Description                                                                                                                       |
      +=============+==================+===================================================================================================================================+
      | permissions | Array of objects | Lists the whitelist records. For details, see :ref:`Table 4 <vpcep_06_0208__table50257079>`.                                      |
      +-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | total_count | Integer          | Specifies the total number of whitelist records that meet the search criteria. The number is not affected by the limit or offset. |
      +-------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0208__table50257079:

   .. table:: **Table 4** permissions parameters

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the permission.                                                                                                                                                                                          |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | permission            | String                | Lists the whitelist records.                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                                     |
      |                       |                       | The permission format is **iam:domain:: 6e9dfd51d1124e8d8498dce894923a0d** or **\***. **\*** indicates all users can connect to the VPC endpoint service. **6e9dfd51d1124e8d8498dce894923a0d** indicates the domain ID of the user. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | description           | String                | Specifies the description of a whitelist record of a VPC endpoint service. The description can contain a maximum of 128 characters and cannot contain left angle brackets (<) or right angle brackets (>).                          |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | permission_type       | String                | Specifies the whitelist type of the VPC endpoint service.                                                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                     |
      |                       |                       | Only **domainId** is supported, which indicates the whitelisted IDs of accounts that can create VPC endpoints to connect to the VPC endpoint service.                                                                               |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies when the whitelist record is added.                                                                                                                                                                                       |
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
                      "description":"demo",
                      "permission_type": "domainId",
                      "created_at":"2018-10-18T13:26:40Z"
                  }
          ],
       "total_count":1
      }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
