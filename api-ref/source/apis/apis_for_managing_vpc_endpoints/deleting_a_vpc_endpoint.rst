:original_name: vpcep_06_0305.html

.. _vpcep_06_0305:

Deleting a VPC Endpoint
=======================

Function
--------

This API is used to delete a VPC endpoint.

URI
---

DELETE /v1/{project_id}/vpc-endpoints/{vpc_endpoint_id}

For detailed about the parameters, see :ref:`Table 1 <vpcep_06_0305__table2452701>`.

.. _vpcep_06_0305__table2452701:

.. table:: **Table 1** Parameters

   +-----------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory | Description                                                                                                                    |
   +=================+===========+================================================================================================================================+
   | project_id      | Yes       | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003_0>`. |
   +-----------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+
   | vpc_endpoint_id | Yes       | Specifies the ID of the VPC endpoint.                                                                                          |
   +-----------------+-----------+--------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  Example request

   This request is to delete the VPC endpoint whose ID is **4189d3c2-8882-4871-a3c2-d380272eed83**.

   .. code-block:: text

      DELETE https://{endpoint}/v1/{project_id}/vpc-endpoints/4189d3c2-8882-4871-a3c2-d380272eed83

Response
--------

None

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
