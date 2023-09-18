:original_name: vpcep_06_0502.html

.. _vpcep_06_0502:

Batch Adding Tags to or Deleting Tags from a Specified Resource
===============================================================

Function
--------

This API is used to batch add tags to or delete tags from a specified VPC endpoint service or VPC endpoint.

-  You can add up to 20 tags to a resource.

URI
---

POST /v1/{project_id}/{resource_type}/{resource_id}/tags/action

:ref:`Table 1 <vpcep_06_0502__table366094812311>` describes parameters in this URI.

.. _vpcep_06_0502__table366094812311:

.. table:: **Table 1** URI parameters

   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter     | Mandatory | Type   | Description                                                                                                                  |
   +===============+===========+========+==============================================================================================================================+
   | project_id    | Yes       | String | Specifies the project ID. For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <vpcep_08_0003>`. |
   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+
   | resource_type | Yes       | String | Specifies the resource type, which can be **endpoint_service** or **endpoint**.                                              |
   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+
   | resource_id   | Yes       | String | Specifies the resource ID, which can be **Endpoint Service ID** or **Endpoint ID**.                                          |
   +---------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   .. table:: **Table 2** Request parameters

      +-----------------+-----------------+--------------------+--------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type               | Description                                                                    |
      +=================+=================+====================+================================================================================+
      | tags            | No              | List<resource_tag> | Lists the tags.                                                                |
      |                 |                 |                    |                                                                                |
      |                 |                 |                    | This parameter is mandatory for common tenants.                                |
      +-----------------+-----------------+--------------------+--------------------------------------------------------------------------------+
      | action          | Yes             | String             | Specifies the operation to be performed, which can be **create** or **delete** |
      +-----------------+-----------------+--------------------+--------------------------------------------------------------------------------+

   .. table:: **Table 3** Data structure of field **resource_tag**

      +-----------------+----------------------------------------------------------------------------------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory                                                                                                            | Type            | Description                                                                                                                                                                                            |
      +=================+======================================================================================================================+=================+========================================================================================================================================================================================================+
      | key             | Yes                                                                                                                  | String          | Specifies the tag key. A tag key contains a maximum of 36 Unicode characters.                                                                                                                          |
      |                 |                                                                                                                      |                 |                                                                                                                                                                                                        |
      |                 |                                                                                                                      |                 | The key meets the requirements in :ref:`Tag Character Set Specifications <vpcep_06_0504>`.                                                                                                             |
      +-----------------+----------------------------------------------------------------------------------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value           | This parameter is mandatory when **action** is set to **create** and optional when **action** is set to **delete**.) | String          | Specifies the tag value. Each value contains a maximum of 43 Unicode characters. If **value** is specified, tags are deleted by key and value. If **value** is not specified, tags are deleted by key. |
      |                 |                                                                                                                      |                 |                                                                                                                                                                                                        |
      |                 |                                                                                                                      |                 | The value meets the requirements in :ref:`Tag Character Set Specifications <vpcep_06_0504>`.                                                                                                           |
      +-----------------+----------------------------------------------------------------------------------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  .. _vpcep_06_0502__li9168649839:

   Example request

   POST https://{endpoint}/v1/{project_id}/endpoint_service/{resource_id}/tags/action

   or https://{endpoint}/v1/{project_id}/endpoint/{resource_id}/tags/action

   POST /v1/{project_id}/{resource_type}/{resource_id}/tags/action

   .. code-block::

      {
          "action": "create",
          "tags": [
              {
                  "key": "key1",
                  "value": "value1"
              },
              {
                  "key": "key",
                  "value": "value3"
              }
      ]
      }

   or

   .. code-block::

      {
          "action": "delete",
          "tags": [
              {
                  "key": "key1"
               },
              {
                  "key": "key2",
                  "value": "value3"
              }
      ]
      }

Response
--------

None

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
