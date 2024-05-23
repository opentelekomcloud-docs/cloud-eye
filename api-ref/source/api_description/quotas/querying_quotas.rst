:original_name: ces_03_0037.html

.. _ces_03_0037:

Querying Quotas
===============

Function
--------

This API is used to query the alarm rule quota and the number of alarm rules that have been created.

URI
---

GET /V1.0/{project_id}/quotas

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

-  Example: Query the alarm rule quota.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/quotas

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 2** Response parameters

      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                        |
      +=======================+=======================+====================================================================+
      | quotas                | Object                | Specifies the quota list.                                          |
      |                       |                       |                                                                    |
      |                       |                       | For details, see :ref:`Table 3 <ces_03_0037__table5856932152840>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------+

   .. _ces_03_0037__table5856932152840:

   .. table:: **Table 3** Data structure description of **quotas**

      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                        |
      +=======================+=======================+====================================================================+
      | resources             | Array of objects      | Specifies the resource quota list.                                 |
      |                       |                       |                                                                    |
      |                       |                       | For details, see :ref:`Table 4 <ces_03_0037__table3902130144815>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------+

   .. _ces_03_0037__table3902130144815:

   .. table:: **Table 4** Data structure description of **resources**

      +-----------------------+-----------------------+------------------------------------------+
      | Parameter             | Type                  | Description                              |
      +=======================+=======================+==========================================+
      | type                  | String                | Specifies the quota type.                |
      |                       |                       |                                          |
      |                       |                       | **alarm** indicates the alarm rule.      |
      +-----------------------+-----------------------+------------------------------------------+
      | used                  | Integer               | Specifies the used amount of the quota.  |
      +-----------------------+-----------------------+------------------------------------------+
      | unit                  | String                | Specifies the quota unit.                |
      +-----------------------+-----------------------+------------------------------------------+
      | quota                 | Integer               | Specifies the total amount of the quota. |
      +-----------------------+-----------------------+------------------------------------------+

-  Example response

   .. code-block::

      {
      "quotas":
          {
          "resources": [
                  {
                      "unit":"",
                      "type":"alarm",
                      "quota":1000,
                      "used":10
                  }
              ]
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
