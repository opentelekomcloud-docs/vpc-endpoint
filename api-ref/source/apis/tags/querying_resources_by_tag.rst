:original_name: vpcep_06_0501.html

.. _vpcep_06_0501:

Querying Resources by Tag
=========================

Function
--------

This API is used to query resources of a tenant by tag.

URI
---

POST /v1/{project_id}/{resource_type}/resource_instances/action

:ref:`Table 1 <vpcep_06_0501__table51771440203117>` describes parameters in this URI.

.. _vpcep_06_0501__table51771440203117:

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

   .. table:: **Table 2** Request parameters

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
      +=================+=================+=================+===========================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
      | tags            | No              | List<tag>       | The resources contain tags listed in **tags** will be queried. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Each tag key and each value of the same tag key must be unique. The response returns resources containing all tags in this list. Keys in this list are in an AND relationship while values in each key-value structure are in an OR relationship. If no tag filtering condition is specified, full data is returned.                   |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tags_any        | No              | List<tag>       | The resources contain any tags listed in **tags_any** will be queried. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Each tag key and each value of the same tag key must be unique. The response returns resources containing the tags in this list. Keys in this list are in an OR relationship and values in each key-value structure are also in an OR relationship. If no tag filtering condition is specified, full data is returned.         |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | not_tags        | No              | List<tag>       | The resources do not contain all the tags listed in **not_tags** will be queried. Each resource to be queried contains a maximum of 20 keys. Each tag key can have a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Each tag key and each value of the same tag key must be unique. The response returns resources containing no tags in this list. Keys in this list are in an AND relationship while values in each key-value structure are in an OR relationship. If no tag filtering condition is specified, full data is returned. |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | not_tags_any    | No              | List<tag>       | The resources do not contain any tag listed in **not_tags_any** will be queried. Each resource to be queried contains a maximum of 20 keys. Each tag key has a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Each tag key and each value of the same tag key must be unique. The response returns resources containing no tags in this list. Keys in this list are in an AND relationship while values in each key-value structure are in an OR relationship. If no tag filtering condition is specified, full data is returned.       |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit           | No              | String          | Sets the page size. This parameter is unavailable when **action** is set to **count**. The default size is **1000** when **action** is set to **filter**. The maximum value is **1000**, and the minimum size is **1**. The size cannot be a negative number.                                                                                                                                                                                                                                                                                                                                                             |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset          | No              | String          | Specifies the index position. This parameter is unavailable when **action** is set to **count**. If **offset** is set to *N*, the resource query starts from the N+1 piece of data. If **action** is set to **filter**, **offset** is **0** by default, indicating that the query starts from the first piece of data. **offset** must be a positive number.                                                                                                                                                                                                                                                              |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | action          | Yes             | String          | Specifies the operation to perform. The operation can only be **filter** (filtering) or **count** (querying the total number).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
      |                 |                 |                 | If **action** is set to **filter**, the query is performed based on the filter conditions. If **action** is set to **count**, only the total number of records is returned.                                                                                                                                                                                                                                                                                                                                                                                                                                               |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | matches         | No              | List<match>     | Specifies the search field. The tag key is the field to be matched, for example, **resource_name**. **value** indicates the matched value. The key is a fixed dictionary value and cannot contain duplicate keys or unsupported keys.                                                                                                                                                                                                                                                                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
      |                 |                 |                 | Check whether fuzzy match is required based on the **key** value. For example, if **key** is set to **resource_name**, fuzzy search (case-insensitive) is performed by default. If **value** is empty, exact match is performed. Most services do not have resources without names. In this case, an empty list is returned. If **key** is **resource_id**, exact match is used. Only **resource_name** for **key** is supported. Other **key** values will be available later.                                                                                                                                           |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 3** Description of field **tag**

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                       |
      +=================+=================+=================+===================================================================================================================================================================================================================================================================================================================================================+
      | key             | Yes             | String          | Specifies the tag key. Each tag key contains a maximum of 127 unicode characters but cannot be left blank. The system does not verify the character set of **key** when searching for resources. **key** cannot be empty, an empty string, or spaces. Before using **key**, delete single-byte character (SBC) spaces before and after the value. |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | values          | Yes             | List<String>    | Specifies the tag value list. Each value contains a maximum of 255 Unicode characters. Before using **values**, delete SBC spaces before and after the value.                                                                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                   |
      |                 |                 |                 | The value can be an empty array but cannot be left blank.                                                                                                                                                                                                                                                                                         |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                   |
      |                 |                 |                 | If the values are null, it indicates **any_value** (querying any value). The values are in the OR relationship.                                                                                                                                                                                                                                   |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                   |
      |                 |                 |                 | The system does not verify the character set of **values** when searching for resources, but only verifies the length.                                                                                                                                                                                                                            |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 4** Description of field **match**

      +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Mandatory | Type   | Description                                                                                                                       |
      +===========+===========+========+===================================================================================================================================+
      | key       | Yes       | String | Specifies the tag key. Only **resource_name** for **key** is supported. Other **key** values will be available later.             |
      +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------+
      | value     | Yes       | String | Specifies the tag value. Each value contains a maximum of 255 Unicode characters. The character set of **value** is not verified. |
      +-----------+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------+

-  .. _vpcep_06_0501__li676964019312:

   Example request

   POST https://{endpoint}/v1/{project_id}/endpoint_service/resource_instances/action

   or POST https://{endpoint}/v1/{project_id}/endpoint/resource_instances/action

   or POST https://{endpoint}/v1/{project_id}/{resource_type}/resource_instances/action

   -  Request body when **action** is set to **filter**

      .. code-block::

         {
             "offset": "100",
             "limit": "100",
             "action": "filter",
             "matches": [
                 {
                     "key": "resource_name",
                     "value": "resource1"
                 }
             ],
             "not_tags": [
                 {
                     "key": "key1",
                     "values": [
                         "*value1",
                         "value2"
                     ]
                 }
             ],
             "tags": [
                 {
                     "key": "key1",
                     "values": [
                         "*value1",
                         "value2"
                     ]
                 }
             ],
             "tags_any": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 }
             ],
             "not_tags_any": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 }
             ]
         }

   -  Request body when **action** is set to **count**

      .. code-block::

         {
             "action": "count",
             "not_tags": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "*value2"
                     ]
                 }
             ],
             "tags": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 },
                 {
                     "key": "key2",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 }
             ],
             "tags_any": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 }
             ],
             "not_tags_any": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 }
             ],
             "matches": [
                 {
                     "key": "resource_name",
                     "value": "resource1"
                 }
             ]
         }

Response
--------

-  Parameter description

   .. table:: **Table 5** Parameter description

      =========== ============== ======================================
      Parameter   Type           Description
      =========== ============== ======================================
      resources   List<resource> N/A
      total_count Integer        Specifies the total number of records.
      =========== ============== ======================================

   .. table:: **Table 6** Data structure of field **resource**

      +---------------+--------------------+----------------------------------------------------------------------------------------+
      | Parameter     | Type               | Description                                                                            |
      +===============+====================+========================================================================================+
      | resource_id   | String             | Specifies the resource ID, which can be **Endpoint Service ID** or **Endpoint ID**.    |
      +---------------+--------------------+----------------------------------------------------------------------------------------+
      | tags          | List<resource_tag> | Lists the tags. If no tag is matched, an empty array is returned.                      |
      +---------------+--------------------+----------------------------------------------------------------------------------------+
      | resource_name | String             | Specifies the resource name. If the resource does not have a name, the ID is returned. |
      +---------------+--------------------+----------------------------------------------------------------------------------------+

   .. table:: **Table 7** Data structure of field **resource_tag**

      ========= ====== ========================
      Parameter Type   Description
      ========= ====== ========================
      key       String Specifies the tag key.
      value     String Specifies the tag value.
      ========= ====== ========================

-  Example response

   -  Response body when **action** is set to **filter**

      .. code-block::

         {
             "resources": [
                 {
                     "resource_detail": null,
                     "resource_id": "cdfs_cefs_wesas_12_dsad",
                     "resource_name": "resource1",
                     "tags": [
                         {
                             "key": "key1","value": "value1"
                         },
                         {
                             "key": "key2","value": "value1"
                         }
                     ]
                 }
             ],
             "total_count": 1000
         }

   -  Response body when **action** is set to **count**

      .. code-block::

         {
             "total_count": 1000
         }

Status Codes
------------

See :ref:`Status Codes <vpcep_08_0001>`.
