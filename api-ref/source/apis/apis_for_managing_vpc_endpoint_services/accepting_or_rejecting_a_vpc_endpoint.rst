:original_name: vpcep_06_0207.html

.. _vpcep_06_0207:

Accepting or Rejecting a VPC Endpoint
=====================================

Function
--------

This API is used to accept or reject a VPC endpoint for a VPC endpoint service.

URI
---

POST /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}/connections/action

:ref:`Table 1 <vpcep_06_0207__table25752879>` describes parameters in this URI.

.. _vpcep_06_0207__table25752879:

.. table:: **Table 1** URI parameters

   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Mandatory | Description                                                                                                                  |
   +=========================+===========+==============================================================================================================================+
   | project_id              | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_service_id | Yes       | Specifies the ID of the VPC endpoint service.                                                                                |
   +-------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   .. table:: **Table 2** Request parameters

      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type             | Description                                                                      |
      +=================+=================+==================+==================================================================================+
      | action          | Yes             | String           | Specifies whether to accept or reject a VPC endpoint for a VPC endpoint service. |
      |                 |                 |                  |                                                                                  |
      |                 |                 |                  | -  **receive**: means to accept the VPC endpoint.                                |
      |                 |                 |                  | -  **reject**: means to reject the VPC endpoint.                                 |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------+
      | endpoints       | Yes             | Array of strings | Lists VPC endpoint IDs.                                                          |
      |                 |                 |                  |                                                                                  |
      |                 |                 |                  | Each request accepts or rejects only one VPC endpoint.                           |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------+

-  Example request

   This request is to accept VPC endpoint **705290f3-0d00-41f2-aedc-71f09844e879** to connect to VPC endpoint service **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      POST https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88/connections/action

   .. code-block::

      {
         "endpoints":["705290f3-0d00-41f2-aedc-71f09844e879"],
         "action": "receive"
      }

Response
--------

-  Parameter description

   .. _vpcep_06_0207__table50476419:

   .. table:: **Table 3** Response parameter

      +-------------+------------------+----------------------------------------------------------------------------------------+
      | Parameter   | Type             | Description                                                                            |
      +=============+==================+========================================================================================+
      | connections | Array of objects | Lists the connections. For details, see :ref:`Table 4 <vpcep_06_0207__table31325900>`. |
      +-------------+------------------+----------------------------------------------------------------------------------------+

   .. _vpcep_06_0207__table31325900:

   .. table:: **Table 4** connection parameters

      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                    |
      +=======================+=======================+================================================================================================================================================================+
      | id                    | String                | Specifies the unique ID of the VPC endpoint.                                                                                                                   |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | marker_id             | Integer               | Specifies the packet ID of the VPC endpoint.                                                                                                                   |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the creation time of the VPC endpoint.                                                                                                               |
      |                       |                       |                                                                                                                                                                |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                             |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the update time of the VPC endpoint.                                                                                                                 |
      |                       |                       |                                                                                                                                                                |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                                                                             |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | domain_id             | String                | Specifies the user's domain ID.                                                                                                                                |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the connection status of the VPC endpoint.                                                                                                           |
      |                       |                       |                                                                                                                                                                |
      |                       |                       | -  **pendingAcceptance**: The VPC endpoint is to be accepted.                                                                                                  |
      |                       |                       | -  **creating**: The VPC endpoint is being created.                                                                                                            |
      |                       |                       | -  **accepted**: The VPC endpoint has been accepted.                                                                                                           |
      |                       |                       | -  **rejected**: The VPC endpoint has been rejected.                                                                                                           |
      |                       |                       | -  **failed**: The VPC endpoint failed to be created.                                                                                                          |
      |                       |                       | -  **deleting**: The VPC endpoint is being deleted.                                                                                                            |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | error                 | Array of objects      | Specifies the error message.                                                                                                                                   |
      |                       |                       |                                                                                                                                                                |
      |                       |                       | This field is returned when the status of the VPC endpoint service changes to **failed**. For details, see :ref:`Table 5 <vpcep_06_0207__table1979118317570>`. |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0207__table1979118317570:

   .. table:: **Table 5** Error parameters

      ============= ====== ============================
      Parameter     Type   Description
      ============= ====== ============================
      error_code    String Specifies the error code.
      error_message String Specifies the error message.
      ============= ====== ============================

-  Example response

   .. code-block::

      {
        "connections":
       [
         {
            "id":"4189d3c2-8882-4871-a3c2-d380272eed83",
            "status":"accepted",
            "marker_id":422321321312321321,
            "domain_id":"6e9dfd51d1124e8d8498dce894923a0d",
            "created_at":"2018-01-30T07:42:01Z",
            "updated_at":"2018-01-30T07:42:01Z"
             }
         ]
      }

   or

   .. code-block::

      {
        "error_code": "Endpoint.2013"
        "error_msg": "The endpoint does not belong to the endpoint service."
      }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
