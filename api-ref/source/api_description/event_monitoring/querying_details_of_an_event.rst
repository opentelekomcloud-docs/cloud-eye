:original_name: ces_03_0075.html

.. _ces_03_0075:

Querying Details of an Event
============================

Function
--------

This API is used to query details of an event based on the event name.

URI
---

GET /V1.0/{project_id}/event/{event_name}

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                                                                                                                                     |
      +=================+=================+=================+=================================================================================================================================================+
      | project_id      | String          | Yes             | Specifies the project ID.                                                                                                                       |
      |                 |                 |                 |                                                                                                                                                 |
      |                 |                 |                 | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`.                                                |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_name      | String          | Yes             | Specifies the event name.                                                                                                                       |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_type      | String          | Yes             | Specifies the event type. The value can be **EVENT.SYS** (system event) or **EVENT.CUSTOM** (custom event).                                     |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_source    | String          | No              | Specifies the event name. The name can be a system event name or a custom event name.                                                           |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_level     | String          | No              | Specifies the event severity. The value can be **Critical**, **Major**, **Minor**, or **Info**.                                                 |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_user      | String          | No              | Specifies the name of the user who reports the event monitoring data. It can also be a project ID.                                              |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_state     | String          | No              | Specifies the event status. The value can be **normal**, **warning**, or **incident**.                                                          |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | from            | Long            | No              | Specifies the start time of the query. The time is a UNIX timestamp and the unit is ms. Example: **1605952700911**                              |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | to              | Long            | No              | Specifies the end time of the query. The time is a UNIX timestamp and the unit is ms. The **from** value must be smaller than the **to** value. |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | start           | Integer         | No              | Specifies the start value of pagination. The value is an integer. The default value is **0**.                                                   |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit           | Integer         | No              | Specifies the maximum number of records that can be queried at a time. Supported range: **1** to **100** (default)                              |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/event/{event_name}

Request
-------

None

Response
--------

-  Response parameters

.. table:: **Table 2** Parameter description

   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type             | Mandatory       | Description                                                                                                                                                                                                                                                                   |
   +=================+==================+=================+===============================================================================================================================================================================================================================================================================+
   | event_name      | String           | No              | Specifies the event name. The name can be a system event name or a custom event name.                                                                                                                                                                                         |
   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_type      | String           | No              | Specifies the event type. The value can be **EVENT.SYS** (system event) or **EVENT.CUSTOM** (custom event).                                                                                                                                                                   |
   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_users     | Array of strings | No              | Specifies the name of the user who reports the event. It can also be a project ID.                                                                                                                                                                                            |
   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_sources   | Array of strings | No              | Specifies the event source. For a system event, the source is the namespace of each service. To view the namespace of each service, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. If the event is a custom event, the event source is defined by the user. |
   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_info      | Array of objects | No              | Specifies details of one or more events.                                                                                                                                                                                                                                      |
   |                 |                  |                 |                                                                                                                                                                                                                                                                               |
   |                 |                  |                 | For details, see :ref:`Table 3 <ces_03_0075__table1062815415499>`.                                                                                                                                                                                                            |
   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | meta_data       | MetaData object  | No              | Specifies the number of metadata records in the query result.                                                                                                                                                                                                                 |
   |                 |                  |                 |                                                                                                                                                                                                                                                                               |
   |                 |                  |                 | For details, see :ref:`Table 6 <ces_03_0075__table642174817533>`.                                                                                                                                                                                                             |
   +-----------------+------------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _ces_03_0075__table1062815415499:

.. table:: **Table 3** **event_info** data structure description

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                                                                                                                                                                                                                                                                                                |
   +=================+=================+=================+============================================================================================================================================================================================================================================================================================================================================================================================================+
   | event_name      | String          | Yes             | Specifies the event name. Start with a letter. Enter 1 to 64 characters. Only letters, digits, and underscores (_) are allowed.                                                                                                                                                                                                                                                                            |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_source    | String          | No              | Specifies the event source in the format of service.item. **service** and **item** each must start with a letter and contain 3 to 32 characters, including only letters, digits, and underscores (_).                                                                                                                                                                                                      |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | time            | Long            | Yes             | Specifies when the event occurred, which is a UNIX timestamp (ms). Since there is a latency between the client and the server, the data timestamp to be inserted should be within the period that starts from one hour before the current time plus 20s to 10 minutes after the current time minus 20s. In this way, the timestamp will be inserted to the database without being affected by the latency. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | detail          | Detail object   | Yes             | Specifies the event details.                                                                                                                                                                                                                                                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                            |
   |                 |                 |                 | For details, see :ref:`Table 4 <ces_03_0075__table415114181224>`.                                                                                                                                                                                                                                                                                                                                          |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_id        | String          | No              | Specifies the event ID.                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _ces_03_0075__table415114181224:

.. table:: **Table 4** **detail** data structure description

   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Type             | Mandatory       | Description                                                                                       |
   +=================+==================+=================+===================================================================================================+
   | content         | String           | No              | Specifies the event content. Enter up to 4,096 characters.                                        |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | group_id        | String           | No              | Specifies the resource group the event belongs to. This ID must be an existing resource group ID. |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | resource_id     | String           | No              | Specifies the resource ID, which can contain a maximum of 128 characters.                         |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | resource_name   | String           | No              | Specifies the resource name, which can contain a maximum of 128 characters.                       |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | event_state     | String           | No              | Specifies the event status.                                                                       |
   |                 |                  |                 |                                                                                                   |
   |                 |                  |                 | The value can be **normal**, **warning**, or **incident**.                                        |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | event_level     | String           | No              | Specifies the event severity.                                                                     |
   |                 |                  |                 |                                                                                                   |
   |                 |                  |                 | The value can be **Critical**, **Major**, **Minor**, or **Info**.                                 |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | event_user      | String           | No              | Specifies the event user. Enter up to 64 characters.                                              |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | event_type      | String           | No              | Specifies the event type.                                                                         |
   |                 |                  |                 |                                                                                                   |
   |                 |                  |                 | The value can be **EVENT.SYS** (system event) or **EVENT.CUSTOM** (custom event).                 |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+
   | dimensions      | Array of objects | No              | Specifies one or more resource dimensions.                                                        |
   |                 |                  |                 |                                                                                                   |
   |                 |                  |                 | For details, see :ref:`Table 5 <ces_03_0075__table18171172815712>`.                               |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------+

.. _ces_03_0075__table18171172815712:

.. table:: **Table 5** **dimensions** data structure description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                                                                                                         |
   +=================+=================+=================+=====================================================================================================================================================================================================================+
   | name            | String          | No              | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value           | String          | No              | Specifies the dimension value, for example, an ECS ID.                                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                                                     |
   |                 |                 |                 | Enter 1 to 256 characters.                                                                                                                                                                                          |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _ces_03_0075__table642174817533:

.. table:: **Table 6** **meta_data** data structure description

   ========= ======= ========= =====================================
   Parameter Type    Mandatory Description
   ========= ======= ========= =====================================
   total     Integer No        Specifies the total number of events.
   ========= ======= ========= =====================================

-  Example response

   .. code-block::

      {
       "event_name": "rebootServer",
       "event_type": "EVENT.SYS",
       "event_users": [
         ""
       ],
       "event_sources": [
         "SYS.ECS"
       ],
       "event_info": [
         {
           "event_id": "ev1606302402256R6doP5YeZ",
           "event_name": "rebootServer",
           "event_source": "SYS.ECS",
           "time": 1606302400000,
           "detail": {
             "content": "{\"resourceSpecCode\":\"kc1.4xlarge.2.linux\",\"enterpriseProjectId\":\"6efb843e-391a-46a8-afc8-7fe51c9dd575\"}",
             "group_id": "",
             "resource_id": "ef8dad27-0488-4de7-bb43-1a0df9806d90",
             "resource_name": "CES-POROS-0001",
             "event_state": "normal",
             "event_level": "Minor",
             "event_user": "",
             "event_type": "EVENT.SYS",
             "dimensions": [
               {
                 "name": "instance_id",
                 "value": "fddad01f-e3b6-420d-8fdc-a42451de7c34"
               }
             ]
           }
         },
         {
           "event_id": "ev1606296088071wGoAOxVYa",
           "event_name": "rebootServer",
           "event_source": "SYS.ECS",
           "time": 1606296086000,
           "detail": {
             "content": "{\"resourceSpecCode\":\"kc1.4xlarge.2.linux\",\"enterpriseProjectId\":\"6efb843e-391a-46a8-afc8-7fe51c9dd575\"}",
             "group_id": "",
             "resource_id": "ef8dad27-0488-4de7-bb43-1a0df9806d90",
             "resource_name": "CES-POROS-0001",
             "event_state": "normal",
             "event_level": "Minor",
             "event_user": "",
             "event_type": "EVENT.SYS",
             "dimensions": [
               {
                 "name": "instance_id",
                 "value": "fddad01f-e3b6-420d-8fdc-a42451de7c34"
               }
             ]
           }
         },
         {
           "event_id": "ev1604654426090g7g37E6Yb",
           "event_name": "rebootServer",
           "event_source": "SYS.ECS",
           "time": 1604654425000,
           "detail": {
             "content": "{\"resourceSpecCode\":\"c6.4xlarge.2.linux\",\"enterpriseProjectId\":\"129559eb-f795-4b5f-9e46-cbd43a462362\"}",
             "group_id": "",
             "resource_id": "0bfa63ee-31f5-40a9-b992-50992c80c58a",
             "resource_name": "ndrv2-pod-ops-0001",
             "event_state": "normal",
             "event_level": "Minor",
             "event_user": "",
             "event_type": "EVENT.SYS",
             "dimensions": [
               {
                 "name": "instance_id",
                 "value": "fddad01f-e3b6-420d-8fdc-a42451de7c34"
               }
             ]
           }
         }
       ],
       "meta_data": {
         "total": 5
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
