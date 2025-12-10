:original_name: ces_03_0021.html

.. _ces_03_0021:

Querying a Specified API Version
================================

Function
--------

This API is used to query a specified API version of Cloud Eye.

URI
---

GET /{api_version}

-  Parameter description

   .. table:: **Table 1** Parameter description

      =========== ========= ==========================
      Parameter   Mandatory Description
      =========== ========= ==========================
      api_version Yes       Specifies the API version.
      =========== ========= ==========================

-  Example

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0\

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 2** Parameter description

      +-----------------------+-----------------------+-------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                       |
      +=======================+=======================+===================================================================+
      | version               | Objects               | Specifies the list of all versions.                               |
      |                       |                       |                                                                   |
      |                       |                       | For details, see :ref:`Table 3 <ces_03_0021__table697164712507>`. |
      +-----------------------+-----------------------+-------------------------------------------------------------------+

   .. _ces_03_0021__table697164712507:

   .. table:: **Table 3** **versions** data structure description

      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                               |
      +=======================+=======================+===========================================================================================================================================================================================================+
      | id                    | String                | Specifies the version ID, for example, v1.                                                                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | links                 | Array of objects      | Specifies the API URL.                                                                                                                                                                                    |
      |                       |                       |                                                                                                                                                                                                           |
      |                       |                       | For details, see :ref:`Table 4 <ces_03_0021__table826514508503>`.                                                                                                                                         |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | version               | String                | Specifies the API version. If the APIs of this version support microversions, set this parameter to the supported maximum microversion. If the microversion is not supported, leave this parameter blank. |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the version status.                                                                                                                                                                             |
      |                       |                       |                                                                                                                                                                                                           |
      |                       |                       | **CURRENT**: indicates a primary version.                                                                                                                                                                 |
      |                       |                       |                                                                                                                                                                                                           |
      |                       |                       | **SUPPORTED**: indicates an old version but is still supported.                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                           |
      |                       |                       | **DEPRECATED**: indicates a deprecated version which may be deleted later.                                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated               | String                | Specifies the version release time, which must be the UTC time. For example, the release time of v1 is **2014-06-28T12:20:21Z**.                                                                          |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | min_version           | String                | If the APIs of this version support microversions, set this parameter to the supported minimum microversion. If not, leave this parameter blank.                                                          |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0021__table826514508503:

   .. table:: **Table 4** **links** data structure description

      +-----------+--------+----------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                            |
      +===========+========+========================================================================================+
      | href      | String | Specifies the reference address of the current API version.                            |
      +-----------+--------+----------------------------------------------------------------------------------------+
      | rel       | String | Specifies the relationship between the current API version and the referenced address. |
      +-----------+--------+----------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "version": {
            "id": "V1.0",
            "links": [
              {
                "href": "https://x.x.x.x/V1.0/",
                "rel": "self"
              }
            ],
            "min_version": "",
            "status": "CURRENT",
            "updated": "2018-09-30T00:00:00Z",
            "version": ""
          }
      }

Returned Values
---------------

-  Normal

   200

-  Abnormal

   +---------------------------+----------------------------------------------------------------------+
   | Returned Value            | Description                                                          |
   +===========================+======================================================================+
   | 400 Bad Request           | Request error.                                                       |
   +---------------------------+----------------------------------------------------------------------+
   | 401 Unauthorized          | The authentication information is not provided or is incorrect.      |
   +---------------------------+----------------------------------------------------------------------+
   | 403 Forbidden             | Access to the requested page is forbidden.                           |
   +---------------------------+----------------------------------------------------------------------+
   | 408 Request Timeout       | The request timed out.                                               |
   +---------------------------+----------------------------------------------------------------------+
   | 429 Too Many Requests     | Concurrent requests are excessive.                                   |
   +---------------------------+----------------------------------------------------------------------+
   | 500 Internal Server Error | Failed to complete the request because of an internal service error. |
   +---------------------------+----------------------------------------------------------------------+
   | 503 Service Unavailable   | The service is currently unavailable.                                |
   +---------------------------+----------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
