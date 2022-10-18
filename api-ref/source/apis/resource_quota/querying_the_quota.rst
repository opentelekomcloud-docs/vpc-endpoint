:original_name: vpcep_06_0401.html

.. _vpcep_06_0401:

Querying the Quota
==================

Function
--------

This API is used to query the quota of your resources, including VPC endpoint services and VPC endpoints.

URI
---

GET /v1/{project_id}/quotas?type={resource_type}

:ref:`Table 1 <vpcep_06_0401__table1148411527716>` describes the required parameters.

.. _vpcep_06_0401__table1148411527716:

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

      +-----------------+-----------------+-----------------+--------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                  |
      +=================+=================+=================+==============================================================+
      | type            | No              | String          | Specifies the resource type.                                 |
      |                 |                 |                 |                                                              |
      |                 |                 |                 | -  **endpoint_service**: indicates the VPC endpoint service. |
      |                 |                 |                 | -  **endpoint**: indicates the VPC endpoint.                 |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------+

-  Example request

   This request is to query the quota of VPC endpoint services.

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/quotas?type=endpoint_service

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-----------+--------+----------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                  |
      +===========+========+==============================================================================================+
      | quotas    | Object | Specifies quota details. For details, see :ref:`Table 4 <vpcep_06_0401__table862171544417>`. |
      +-----------+--------+----------------------------------------------------------------------------------------------+

   .. _vpcep_06_0401__table862171544417:

   .. table:: **Table 4** Quotas description

      +-----------+------------------+-------------------------------------------------------------------------------------------+
      | Parameter | Type             | Description                                                                               |
      +===========+==================+===========================================================================================+
      | resources | Array of objects | Lists the resources. For details, see :ref:`Table 5 <vpcep_06_0401__table1170141514413>`. |
      +-----------+------------------+-------------------------------------------------------------------------------------------+

   .. _vpcep_06_0401__table1170141514413:

   .. table:: **Table 5** Resource parameters

      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                          |
      +=======================+=======================+======================================================================================================================+
      | type                  | String                | Specifies the resource type. You can query the quota of resources of a specified type by configuring this parameter. |
      |                       |                       |                                                                                                                      |
      |                       |                       | -  **endpoint_service**: indicates the VPC endpoint service.                                                         |
      |                       |                       | -  **endpoint**: indicates the VPC endpoint.                                                                         |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------+
      | used                  | Integer               | Specifies the number of created resources.                                                                           |
      |                       |                       |                                                                                                                      |
      |                       |                       | The value ranges from **0** to the value of **quota**.                                                               |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------+
      | quota                 | Integer               | Specifies the maximum quota of resources.                                                                            |
      |                       |                       |                                                                                                                      |
      |                       |                       | The value ranges from the default quota value to the maximum quota value.                                            |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
      "quotas":{
           "resources":[
                       {
                           "type":"endpoint",
                           "used":4,
                           "quota":150
                      },
                       {
                           "type":"endpoint_service",
                           "used":10,
                           "quota": 100
                      }
                    ]
              }
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
