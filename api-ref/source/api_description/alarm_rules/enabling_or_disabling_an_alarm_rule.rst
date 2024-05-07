:original_name: ces_03_0029.html

.. _ces_03_0029:

Enabling or Disabling an Alarm Rule
===================================

Function
--------

This API is used to enable or disable an alarm rule.

URI
---

PUT /V1.0/{project_id}/alarms/{alarm_id}/action

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | alarm_id              | Yes                   | Specifies the alarm rule ID.                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      PUT https://{Cloud Eye endpoint}/V1.0/{project_id}/alarms/al1441967036681YkazZ0deN/action

Request
-------

-  Request parameters

   .. table:: **Table 2** Request parameters

      +-----------------+-----------------+-----------------+----------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                              |
      +=================+=================+=================+==========================================================+
      | alarm_enabled   | Yes             | Boolean         | Specifies whether the alarm rule is enabled.             |
      |                 |                 |                 |                                                          |
      |                 |                 |                 | -  **true**: indicates that the alarm rule is enabled.   |
      |                 |                 |                 | -  **false**: indicates that the alarm rule is disabled. |
      +-----------------+-----------------+-----------------+----------------------------------------------------------+

-  Example request

   .. code-block::

      {
          "alarm_enabled":true
      }

Response
--------

The response has no message body.

Returned Values
---------------

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
