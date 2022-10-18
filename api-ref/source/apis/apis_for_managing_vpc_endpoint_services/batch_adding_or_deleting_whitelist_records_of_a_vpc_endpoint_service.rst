:original_name: vpcep_06_0209.html

.. _vpcep_06_0209:

Batch Adding or Deleting Whitelist Records of a VPC Endpoint Service
====================================================================

Function
--------

This API is used to batch add to or delete whitelist records from a VPC endpoint service.

.. note::

   Your domain ID is in the whitelist of your own VPC endpoint service by default.

URI
---

POST /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}/permissions/action

:ref:`Table 1 <vpcep_06_0209__table16108480>` describes the required parameters.

.. _vpcep_06_0209__table16108480:

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

      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type             | Description                                                                                                                                                                       |
      +=================+=================+==================+===================================================================================================================================================================================+
      | permissions     | Yes             | Array of strings | Lists the whitelist records.                                                                                                                                                      |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  | The record is in the **iam:domain::**\ *domain_id* format.                                                                                                                        |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  | Fields are described as follows:                                                                                                                                                  |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  | -  **iam:domain::** is fixed.                                                                                                                                                     |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  | -  *domain_id* indicates the domain ID of the target user.                                                                                                                        |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  |    The value contains 1 to 64 characters, including letters, digits, and asterisks (*). If you enter an asterisk, this VPC endpoint service allows access from any VPC endpoints. |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  |    Example: **iam:domain::6e9dfd51d1124e8d8498dce894923a0dd**                                                                                                                     |
      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | action          | Yes             | String           | Specifies the operation to be performed.                                                                                                                                          |
      |                 |                 |                  |                                                                                                                                                                                   |
      |                 |                 |                  | The value is **add** or **remove**.                                                                                                                                               |
      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   This request is to add a whitelist record to the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      POST https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88/permissions/action

   .. code-block::

      {
          "permissions":
            [
              "iam:domain::fc973eea581490997e82ea11a1d0101"
            ],
          "action":"add"
      }

   This request is to delete a whitelist record from the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      POST https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88/iam:domain::5fc973eea581490997e82ea11a1d0101/action

   .. code-block::

      {
        "permissions":
          [
            "iam:domain::5fc973eea581490997e82ea11a1d0101"
          ],
         "action":"remove"
      }

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================================+
      | permissions           | Array of strings      | Lists the whitelist records.                                                                                                                                                                                                        |
      |                       |                       |                                                                                                                                                                                                                                     |
      |                       |                       | The permission format is **iam:domain:: 6e9dfd51d1124e8d8498dce894923a0d** or **\***. **\*** indicates all users can connect to the VPC endpoint service. **6e9dfd51d1124e8d8498dce894923a0d** indicates the domain ID of the user. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "permissions":
          [
            "iam:domain::5fc973eea581490997e82ea11a1d0101",
            "iam:domain::5fc973eea581490997e82ea11a1d0102"
            ]
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
