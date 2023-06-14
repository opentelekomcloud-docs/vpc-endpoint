:original_name: vpcep_06_0302.html

.. _vpcep_06_0302:

Querying Basic Information About a VPC Endpoint Service
=======================================================

Function
--------

This API is used to query basic information about a target VPC endpoint service. You can use this API to query the target VPC endpoint service to be accessed. This API can also be used by other users to query basic information about your VPC endpoint service, without exposing your server information.

URI
---

GET /v1/{project_id}/vpc-endpoint-services/describe?endpoint_service_name={endpoint_service_name}&id={endpoint_service_id}

:ref:`Table 1 <vpcep_06_0302__table19259243>` describes the parameter in this URI.

.. _vpcep_06_0302__table19259243:

.. table:: **Table 1** URI parameter

   +------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Description                                                                                                                  |
   +============+===========+==============================================================================================================================+
   | project_id | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +------------+-----------+------------------------------------------------------------------------------------------------------------------------------+

.. _vpcep_06_0302__table16494874:

.. table:: **Table 2** Query parameters

   +-----------------------+---------------------------------------------------------------------------------------+-----------------+------------------------------------------------------+
   | Parameter             | Mandatory                                                                             | Type            | Description                                          |
   +=======================+=======================================================================================+=================+======================================================+
   | endpoint_service_name | No                                                                                    | String          | Specifies the name of the VPC endpoint service.      |
   |                       |                                                                                       |                 |                                                      |
   |                       | .. note::                                                                             |                 |                                                      |
   |                       |                                                                                       |                 |                                                      |
   |                       |    Either this parameter or the **id** parameter must be selected.                    |                 |                                                      |
   +-----------------------+---------------------------------------------------------------------------------------+-----------------+------------------------------------------------------+
   | id                    | No                                                                                    | String          | Specifies the unique ID of the VPC endpoint service. |
   |                       |                                                                                       |                 |                                                      |
   |                       | .. note::                                                                             |                 |                                                      |
   |                       |                                                                                       |                 |                                                      |
   |                       |    Either this parameter or the **endpoint_service_name** parameter must be selected. |                 |                                                      |
   +-----------------------+---------------------------------------------------------------------------------------+-----------------+------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  .. _vpcep_06_0302__li189061227201719:

   Example request

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/vpc-endpoint-services/describe?id=4189d3c2-8882-4871-a3c2-d380272eed83

Response
--------

-  Parameter description

   .. table:: **Table 3** Response parameters

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint service.                                                                                                                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_name          | String                | Specifies the name of the VPC endpoint service.                                                                                                                                                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | service_type          | String                | Specifies the type of the VPC endpoint service. Only your private services can be configured into interface VPC endpoint services.                                                                               |
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
        "id": "9d4c1028-1336-4556-9881-b5d807c1b8a8",
        "service_name": "test123",
        "service_type": "interface",
        "created_at": "2018-09-17T07:28:31Z",
        "is_charge": "true"
      }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
