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

:ref:`Table 1 <vpcep_06_0503__table943516221477>` describes the required parameters.

.. _vpcep_06_0503__table943516221477:

.. table:: **Table 1** Parameter description

   +---------------+-----------+--------+---------------------------------------------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                                                     |
   +===============+===========+========+=================================================================================+
   | project_id    | Yes       | String | Specifies the project ID.                                                       |
   +---------------+-----------+--------+---------------------------------------------------------------------------------+
   | resource_type | Yes       | String | Specifies the resource type. The value is **endpoint_service** or **endpoint**. |
   +---------------+-----------+--------+---------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   None

-  Example request

   GET https://127.0.0.1:7443/v1/{project_id}/endpoint_service/tags

   or https://127.0.0.1:7443/v1/{project_id}/endpoint/tags GET /v1/{project_id}/{resource_type}/tags

Response
--------

-  Parameter description

   .. table:: **Table 2** Response parameters

      ========= ========= ================== ===============
      Parameter Mandatory Type               Description
      ========= ========= ================== ===============
      tags      Yes       List<resource_tag> Lists the tags.
      ========= ========= ================== ===============

   .. table:: **Table 3** Data structure of field **resource_tag**

      ========= ========= ============ ======================
      Parameter Mandatory Type         Description
      ========= ========= ============ ======================
      key       Yes       String       Specifies the tag key.
      values    Yes       List<String> Lists the tag values.
      ========= ========= ============ ======================

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

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
