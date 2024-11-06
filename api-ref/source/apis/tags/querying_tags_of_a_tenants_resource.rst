:original_name: vpcep_06_0503.html

.. _vpcep_06_0503:

Querying Tags of a Tenant's Resource
====================================

Function
--------

This API is used to obtain tags of resources of a tenant based on the tenant ID and resource type.

URI
---

GET /v1/{project_id}/{resource_type}/tags

:ref:`Table 1 <vpcep_06_0503__table943516221477>` describes parameters in this URI.

.. _vpcep_06_0503__table943516221477:

.. table:: **Table 1** URI parameters

   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                                                                                                  |
   +===============+===========+========+==============================================================================================================================+
   | project_id    | Yes       | String | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+
   | resource_type | Yes       | String | Specifies the resource type, which can be **endpoint_service** or **endpoint**.                                              |
   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  .. _vpcep_06_0503__li1874735215517:

   Example request

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/endpoint_service/tags

   or

   .. code-block:: text

      GET https://{endpoint}/v1/{project_id}/endpoint/tags

Response
--------

-  Parameter description

   .. table:: **Table 2** Response parameter

      ========= ========= ================== ===============
      Parameter Mandatory Type               Description
      ========= ========= ================== ===============
      tags      Yes       List<resource_tag> Lists the tags.
      ========= ========= ================== ===============

   .. table:: **Table 3** Data structure of field **resource_tag**

      ========= ========= ============ =============================
      Parameter Mandatory Type         Description
      ========= ========= ============ =============================
      key       Yes       String       Specifies the tag key.
      values    Yes       List<String> Specifies the tag value list.
      ========= ========= ============ =============================

-  Example response

   .. code-block::

      {
          "tags": [
              {
                  "key": "key1",
                  "values": [
                      "*value1",
                      "value2"
                  ]
              }
          ]
      }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
