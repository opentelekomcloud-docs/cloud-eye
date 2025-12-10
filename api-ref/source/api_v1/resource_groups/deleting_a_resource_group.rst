:original_name: ces_03_0072.html

.. _ces_03_0072:

Deleting a Resource Group
=========================

Function
--------

This API is used to delete a resource group.

URI
---

DELETE /V1.0/{project_id}/resource-groups/{group_id}

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                                                                                      |
      +=================+=================+=================+==================================================================================================+
      | project_id      | String          | Yes             | Specifies the project ID.                                                                        |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | Minimum: **1**                                                                                   |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | Maximum: **64**                                                                                  |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | **Regular expression matching**: ^[a-zA-Z0-9-]{1,64}$                                            |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+
      | group_id        | String          | Yes             | Specifies the resource group ID.                                                                 |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+

-  Request example

   .. code-block:: text

      DELETE https://{Cloud Eye endpoint}/V1.0/{project_id}/resource-groups/{group_id}

Request
-------

None

Response
--------

None

Returned Value
--------------

-  Normal

   204

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
