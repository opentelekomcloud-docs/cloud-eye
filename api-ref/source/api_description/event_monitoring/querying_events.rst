:original_name: ces_03_0074.html

.. _ces_03_0074:

Querying Events
===============

Function
--------

This API is used to query events, including system events and custom events.

URI
---

GET /V1.0/{project_id}/events

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                                                                                                                                                               |
      +=================+=================+=================+===========================================================================================================================================================================+
      | project_id      | String          | Yes             | Specifies the project ID.                                                                                                                                                 |
      |                 |                 |                 |                                                                                                                                                                           |
      |                 |                 |                 | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`.                                                                          |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_type      | String          | No              | Specifies the event type. Possible types are **EVENT.SYS** (system event) and **EVENT.CUSTOM** (custom event).                                                            |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_name      | String          | No              | Specifies the event name. The name can be a system event name or a custom event name.                                                                                     |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | from            | Integer         | No              | Specifies the start time of the query. The time is a UNIX timestamp and the unit is ms. Example: **1605952700911**                                                        |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | to              | Integer         | No              | Specifies the end time of the query. The time is a UNIX timestamp and the unit is ms. **from** must be smaller than **to**. For example, set **to** to **1606557500911**. |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | start           | Integer         | No              | Specifies the start value of pagination. The value is an integer. The default value is **0**.                                                                             |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit           | Integer         | No              | Specifies the maximum number of events that can be queried at a time. Supported range: **1** to **100** (default)                                                         |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/events

Request
-------

None

Response
--------

-  Response parameters

.. table:: **Table 2** Parameter description

   +-----------------+-------------------------+-----------------+--------------------------------------------------------------------+
   | Parameter       | Type                    | Mandatory       | Description                                                        |
   +=================+=========================+=================+====================================================================+
   | events          | Array of Events objects | No              | Specifies one or more pieces of event data.                        |
   |                 |                         |                 |                                                                    |
   |                 |                         |                 | For details, see :ref:`Table 3 <ces_03_0074__table1062815415499>`. |
   +-----------------+-------------------------+-----------------+--------------------------------------------------------------------+
   | meta_data       | MetaData object         | No              | Specifies the number of metadata records in the query result.      |
   |                 |                         |                 |                                                                    |
   |                 |                         |                 | For details, see :ref:`Table 4 <ces_03_0074__table642174817533>`.  |
   +-----------------+-------------------------+-----------------+--------------------------------------------------------------------+

.. _ces_03_0074__table1062815415499:

.. table:: **Table 3** **events** field description

   +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Type            | Mandatory       | Description                                                                                                                                                                          |
   +=====================+=================+=================+======================================================================================================================================================================================+
   | event_name          | String          | No              | Specifies the event name.                                                                                                                                                            |
   +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_type          | String          | No              | Specifies the event type.                                                                                                                                                            |
   +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | event_count         | Integer         | No              | Specifies the number of occurrences of this event within the specified query time range.                                                                                             |
   +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | latest_occur_time   | Long            | No              | Specifies when the event last occurred.                                                                                                                                              |
   +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | latest_event_source | String          | No              | If the event is a system event, the source is the namespace of each service. To view the namespace of each service, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
   |                     |                 |                 |                                                                                                                                                                                      |
   |                     |                 |                 | If the event is a custom event, the event source is defined by the user.                                                                                                             |
   +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _ces_03_0074__table642174817533:

.. table:: **Table 4** **meta_data** data structure description

   ========= ======= ========= =====================================
   Parameter Type    Mandatory Description
   ========= ======= ========= =====================================
   total     Integer No        Specifies the total number of events.
   ========= ======= ========= =====================================

-  Example response

   .. code-block::

      {
       "events": [
         {
           "event_name": "rebootServer",
           "event_type": "EVENT.SYS",
           "event_count": 5,
           "latest_occur_time": 1606302400000,
           "latest_event_source": "SYS.ECS"
         },
         {
           "event_name": "deleteVolume",
           "event_type": "EVENT.SYS",
           "event_count": 6,
           "latest_occur_time": 1606300359126,
           "latest_event_source": "SYS.EVS"
         },
         {
           "event_name": "event_001",
           "event_type": "EVENT.CUSTOM",
           "event_count": 4,
           "latest_occur_time": 1606499035522,
           "latest_event_source": "TEST.System"
         }
       ],
       "meta_data": {
         "total": 10
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
