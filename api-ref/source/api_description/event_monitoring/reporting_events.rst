:original_name: en-us_topic_0109034020.html

.. _en-us_topic_0109034020:

Reporting Events
================

Function
--------

An API for reporting custom events is provided, which helps you collect and report abnormal events or important change events to Cloud Eye.

URI
---

POST /V1.0/{project_id}/events

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      POST https://{Cloud Eye endpoint}/V1.0/{project_id}/events

Request
-------

-  Request parameters

   .. table:: **Table 2** Parameter description

      +-----------------+--------------------------------------------------------------------------------+-----------+---------------------------+
      | Parameter       | Type                                                                           | Mandatory | Description               |
      +=================+================================================================================+===========+===========================+
      | [Array element] | Array of :ref:`EventItem <en-us_topic_0109034020__table3736458191816>` objects | Yes       | Specifies the event list. |
      +-----------------+--------------------------------------------------------------------------------+-----------+---------------------------+

   .. _en-us_topic_0109034020__table3736458191816:

   .. table:: **Table 3** Parameter description of the **EventItem** field

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                |
      +=================+=================+=================+============================================================================================================================================================================================================================================================================================================================================+
      | event_name      | Yes             | String          | Specifies the event name.                                                                                                                                                                                                                                                                                                                  |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 | Start with a letter. Enter 1 to 64 characters. Only letters, digits, and underscores (_) are allowed.                                                                                                                                                                                                                                      |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_source    | Yes             | String          | Specifies the event source.                                                                                                                                                                                                                                                                                                                |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 | The format is service.item. Set this parameter based on the site requirements.                                                                                                                                                                                                                                                             |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 | **service** and **item** each must be a string that starts with a letter and contains 3 to 32 characters, including only letters, digits, and underscores (_).                                                                                                                                                                             |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | time            | Yes             | Long            | Specifies when the event occurred, which is a UNIX timestamp (ms).                                                                                                                                                                                                                                                                         |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 | .. note::                                                                                                                                                                                                                                                                                                                                  |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 |    Since there is a latency between the client and the server, the data timestamp to be inserted should be within the period that starts from one hour before the current time plus 20s to 10 minutes after the current time minus 20s. In this way, the timestamp will be inserted to the database without being affected by the latency. |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 |    For example, if the current time is 2020.01.30 12:00:30, the timestamp inserted must be within the range [2020.01.30 11:00:50, 2020.01.30 12:10:10]. The corresponding UNIX timestamp is [1580353250, 1580357410].                                                                                                                      |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | detail          | Yes             | Detail object   | Specifies the event details.                                                                                                                                                                                                                                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                 | For details, see :ref:`Table 4 <en-us_topic_0109034020__table181310172506>`.                                                                                                                                                                                                                                                               |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0109034020__table181310172506:

   .. table:: **Table 4** **detail** data structure description

      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                     |
      +=================+=================+=================+=================================================================================================================================================================+
      | content         | No              | String          | Specifies the event content. Enter up to 4,096 characters.                                                                                                      |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_id     | No              | String          | Specifies the resource ID. Enter up to 128 characters, including letters, digits, underscores (_), hyphens (-), and colon (:).                                  |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | Example: 6a69bf28-ee62-49f3-9785-845dacd799ec                                                                                                                   |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | To query the resource ID, perform the following steps:                                                                                                          |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | #. Log in to the management console.                                                                                                                            |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | #. Under **Computing**, select **Elastic Cloud Server**.                                                                                                        |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 |    On the **Resource Overview** page, obtain the resource ID.                                                                                                   |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_name   | No              | String          | Specifies the resource name. Enter up to 128 characters, including letters, digits, underscores (_), hyphens (-), and periods (.).                              |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_state     | No              | String          | Specifies the event status.                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | The value can be **normal**, **warning**, or **incident**.                                                                                                      |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_level     | No              | String          | Specifies the event severity.                                                                                                                                   |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | The value can be **Critical**, **Major**, **Minor**, or **Info**.                                                                                               |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_user      | No              | String          | Specifies the event user.                                                                                                                                       |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | Enter up to 64 characters, including letters, digits, underscores (_), hyphens (-), slashes (/), and spaces.                                                    |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_type      | No              | String          | Specifies the event type.                                                                                                                                       |
      |                 |                 |                 |                                                                                                                                                                 |
      |                 |                 |                 | Its value can be **EVENT.SYS** or **EVENT.CUSTOM**. **EVENT.SYS** indicates system events that cannot be reported by users. Only custom events can be reported. |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      [{
          "event_name":"systemInvaded",
          "event_source":"financial.System",
          "time":1522121194000,
          "detail":{
              "content":"The financial system was invaded",
              "group_id":"rg15221211517051YWWkEnVd",
              "resource_id":"1234567890sjgggad",
              "resource_name":"ecs001",
              "event_state":"normal",
              "event_level":"Major",
              "event_user":"xiaokong",
              "event_type": "EVENT.CUSTOM"
          }
      },
      {
          "event_name":"systemInvaded",
          "event_source":"financial.System",
          "time":1522121194020,
          "detail":{
              "content":"The financial system was invaded",
              "group_id":"rg15221211517051YWWkEnVd",
              "resource_id":"1234567890sjgggad",
              "resource_name":"ecs001",
              "event_state":"normal",
              "event_level":"Major",
              "event_user":"xihong",
              "event_type": "EVENT.CUSTOM"
          }
      }]

Response
--------

-  Response parameters

   .. table:: **Table 5** Parameter description

      +-----------------------+-----------------------+-------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                   |
      +=======================+=======================+===============================================================================+
      | Array elements        | Array of objects      | Specifies the event list.                                                     |
      |                       |                       |                                                                               |
      |                       |                       | For details, see :ref:`Table 6 <en-us_topic_0109034020__table7651809184830>`. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------+

   .. _en-us_topic_0109034020__table7651809184830:

   .. table:: **Table 6** Response parameters

      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                           |
      +=================+=================+=================+=======================================================================================================+
      | event_id        | Yes             | String          | Specifies the event ID.                                                                               |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------+
      | event_name      | Yes             | String          | Specifies the event name.                                                                             |
      |                 |                 |                 |                                                                                                       |
      |                 |                 |                 | Start with a letter. Enter 1 to 64 characters. Only letters, digits, and underscores (_) are allowed. |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      [
             {
                  "event_id":"evdgiqwgedkkcvhdjcdu346",
                  "event_name":"systemInvaded"
              },
              {
                  "event_id":"evdgiqwgedkkcvhdjcdu347",
                  "event_name":"systemParalysis"
              }
      ]

Returned Values
---------------

-  Normal

   201

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
