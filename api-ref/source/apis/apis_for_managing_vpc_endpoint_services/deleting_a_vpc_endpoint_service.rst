:original_name: vpcep_06_0204.html

.. _vpcep_06_0204:

Deleting a VPC Endpoint Service
===============================

Function
--------

This API is used to delete a VPC endpoint service.

URI
---

DELETE /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}

:ref:`Table 1 <vpcep_06_0204__table35049127>` describes the required parameters.

.. _vpcep_06_0204__table35049127:

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

   None

-  Example request

   This request is to delete the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      DELETE https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88

Response
--------

None

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
