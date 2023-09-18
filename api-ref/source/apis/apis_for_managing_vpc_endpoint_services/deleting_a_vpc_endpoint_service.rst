:original_name: vpcep_06_0204.html

.. _vpcep_06_0204:

Deleting a VPC Endpoint Service
===============================

.. _vpcep_06_0204__section17315029:

Function
--------

This API is used to delete a VPC endpoint service.

.. note::

   This API is asynchronous. If it is successfully invoked, status code **200** is returned, indicating that the request has been successfully delivered. It takes 1 to 2 minutes to delete a VPC endpoint service. You can view the deletion result by performing operations in :ref:`Querying Details About a VPC Endpoint Service <vpcep_06_0202>`.

URI
---

DELETE /v1/{project_id}/vpc-endpoint-services/{vpc_endpoint_service_id}

:ref:`Table 1 <vpcep_06_0204__table35049127>` describes parameters in this URI.

.. _vpcep_06_0204__table35049127:

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

   None

-  Example request

   This request is to delete the VPC endpoint service whose ID is **4189d3c2-8882-4871-a3c2-d380272eed88**.

   .. code-block:: text

      DELETE https://{endpoint}/v1/{project_id}/vpc-endpoint-services/4189d3c2-8882-4871-a3c2-d380272eed88

Response
--------

None

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
