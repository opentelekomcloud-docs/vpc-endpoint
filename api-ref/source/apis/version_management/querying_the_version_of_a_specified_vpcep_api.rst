:original_name: vpcep_06_0102.html

.. _vpcep_06_0102:

Querying the Version of a Specified VPCEP API
=============================================

Function
--------

This API is used to query the version of a specified VPCEP API.

URI
---

GET /{version}

Request
-------

-  Parameters

   .. table:: **Table 1** Request parameters

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                    |
      +=================+=================+=================+================================================================================+
      | version         | No              | String          | Specifies the version to be queried. The value starts with v, for example, v1. |
      |                 |                 |                 |                                                                                |
      |                 |                 |                 | If this parameter is left blank, versions of all APIs are queried.             |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------+

-  Example request

   GET https://{endpoint}/v1

Response
--------

-  Parameters

   .. table:: **Table 2** Response parameters

      +-----------+--------+------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                          |
      +===========+========+======================================================================================================+
      | version   | Object | Lists the versions of VPCEP APIs. For details, see :ref:`Table 3 <vpcep_06_0102__table13687304356>`. |
      +-----------+--------+------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0102__table13687304356:

   .. table:: **Table 3** **VersionModel** parameters

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                           |
      +=======================+=======================+=======================================================================================================+
      | status                | String                | Specifies the version status.                                                                         |
      |                       |                       |                                                                                                       |
      |                       |                       | -  **CURRENT**: indicates a major version.                                                            |
      |                       |                       | -  **SUPPORT**: indicates an earlier version which is still supported.                                |
      |                       |                       | -  **DEPRECATED**: indicates a deprecated version that may be deleted later.                          |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+
      | id                    | String                | Specifies the version ID.                                                                             |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+
      | updated               | String                | Specifies the time when the API version was released.                                                 |
      |                       |                       |                                                                                                       |
      |                       |                       | The UTC time format is used: YYYY-MM-DDTHH:MM:SSZ.                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+
      | version               | String                | Specifies the supported version.                                                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+
      | min_version           | String                | Specifies the microversion number. If the APIs do not support microversions, the value is left blank. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+
      | links                 | Array of objects      | Specifies the API URL. For details, see :ref:`Table 4 <vpcep_06_0102__table2072420713363>`.           |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------+

   .. _vpcep_06_0102__table2072420713363:

   .. table:: **Table 4** **VersionLink** parameters

      +-----------+--------+-----------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                   |
      +===========+========+===============================================================================================+
      | href      | String | Specifies the reference address of the current API version.                                   |
      +-----------+--------+-----------------------------------------------------------------------------------------------+
      | type      | String | Specifies the MIME type of the entity sending the request. The value is **application/json**. |
      +-----------+--------+-----------------------------------------------------------------------------------------------+
      | rel       | String | Specifies the relationship between the current API version and the referenced address.        |
      +-----------+--------+-----------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "version":{
          {
            "updated":"2018-09-30T00:00:00Z",
            "version":"1",
            "min_version":"",
            "status":"CURRENT",
            "id":"v1",
            "links":[
              {
                "href":"https://{vpcep_uri}/v1",
                "type":"application/json",
                "rel":"self"
              }
            ]
          }
        }
      }

Status Code
-----------

For details about status codes, see :ref:`Status Code <vpcep_08_0001>`.
