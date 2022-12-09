:original_name: ces_03_0027.html

.. _ces_03_0027:

Querying Alarm Rules
====================

Function
--------

This API is used to query the alarm rule list. You can specify the paging parameters to limit the number of query results displayed on a page. You can also set the sorting order of query results.

URI
---

GET /V1.0/{project_id}/alarms

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

   .. table:: **Table 2** Parameter description

      +-----------------------+-----------------------+---------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                   |
      +=======================+=======================+===============================================================+
      | alarms                | Array of objects      | Specifies the alarm rule list.                                |
      |                       |                       |                                                               |
      |                       |                       | For details, see :ref:`Table 3 <ces_03_0027__table35416756>`. |
      +-----------------------+-----------------------+---------------------------------------------------------------+

   .. _ces_03_0027__table35416756:

   .. table:: **Table 3** Query parameter description

      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                           |
      +=================+=================+=================+=======================================================================+
      | start           | No              | String          | Specifies the first queried alarm to be displayed on a page.          |
      |                 |                 |                 |                                                                       |
      |                 |                 |                 | The value is **alarm_id**.                                            |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------+
      | limit           | No              | Integer         | Supported range: **1** to **100** (default)                           |
      |                 |                 |                 |                                                                       |
      |                 |                 |                 | This parameter is used to limit the number of query results.          |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------+
      | order           | No              | String          | Specifies the result sorting method, which is sorted by timestamp.    |
      |                 |                 |                 |                                                                       |
      |                 |                 |                 | The default method is **desc**.                                       |
      |                 |                 |                 |                                                                       |
      |                 |                 |                 | -  **asc**: The query results are displayed in the ascending order.   |
      |                 |                 |                 | -  **desc**: The query results are displayed in the descending order. |
      +-----------------+-----------------+-----------------+-----------------------------------------------------------------------+

-  Example

   Request example 1: Query the current alarm rule list.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/alarms

   Request example 2: Query the alarm rule list. Start by setting **alarm_id** to **al1441967036681YkazZ0deN** and retain 10 records in the descending order of time stamps.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/alarms?start=al1441967036681YkazZ0deN&limit=10&order=desc

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 4** Response parameters

      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                    |
      +=======================+=======================+================================================================================+
      | metric_alarms         | Array of objects      | Specifies the list of alarm objects.                                           |
      |                       |                       |                                                                                |
      |                       |                       | For details, see :ref:`Table 5 <ces_03_0027__table10571837131516>`.            |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | meta_data             | Object                | Specifies the metadata of query results, including the pagination information. |
      |                       |                       |                                                                                |
      |                       |                       | For details, see :ref:`Table 11 <ces_03_0027__table1933614411408>`.            |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+

   .. _ces_03_0027__table10571837131516:

   .. table:: **Table 5** **metric_alarms** data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                            |
      +=======================+=======================+========================================================================================================================================================+
      | alarm_name            | String                | Specifies the alarm rule name.                                                                                                                         |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_description     | String                | Provides supplementary information about the alarm rule.                                                                                               |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric                | Object                | Specifies the alarm metric.                                                                                                                            |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 6 <ces_03_0027__table19174559133918>`.                                                                                    |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | condition             | Object                | Specifies the alarm triggering condition.                                                                                                              |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 10 <ces_03_0027__table1473091124015>`.                                                                                    |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_enabled         | Boolean               | Specifies whether to enable the alarm rule.                                                                                                            |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_level           | Integer               | Specifies the alarm severity, which can be **1**, **2** (default), **3** or **4**, indicating critical, major, minor, and informational, respectively. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_action_enabled  | Boolean               | Specifies whether to enable the action to be triggered by an alarm.                                                                                    |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_actions         | Array of objects      | Specifies the action to be triggered by an alarm.                                                                                                      |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 8 <ces_03_0027__table569133710159>`.                                                                                      |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ok_actions            | Array of objects      | Specifies the action to be triggered after the alarm is cleared.                                                                                       |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 9 <ces_03_0027__table1819115871510>`.                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_id              | String                | Specifies the alarm rule ID.                                                                                                                           |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | update_time           | long                  | Specifies when the alarm status changed. The time is a UNIX timestamp and the unit is ms.                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_state           | String                | Specifies the alarm status, which can be                                                                                                               |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | -  **ok**: The alarm status is normal.                                                                                                                 |
      |                       |                       | -  **alarm**: An alarm is generated.                                                                                                                   |
      |                       |                       | -  **insufficient_data**: The required data is insufficient.                                                                                           |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0027__table19174559133918:

   .. table:: **Table 6** **metric** data structure description

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                           |
      +=======================+=======================+=======================================================================================================================================================================================================+
      | namespace             | String                | Query the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions            | Array of objects      | Specifies the list of metric dimensions.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                       |
      |                       |                       | For details, see :ref:`Table 7 <ces_03_0027__table7554143164419>`.                                                                                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name           | String                | Specifies the metric ID. For example, if the monitoring metric of an ECS is CPU usage, **metric_name** is **cpu_util**. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0027__table7554143164419:

   .. table:: **Table 7** **dimensions** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================+
      | name                  | String                | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value                 | String                | Specifies the dimension value, for example, an ECS ID.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                     |
      |                       |                       | Enter 1 to 256 characters.                                                                                                                                                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0027__table569133710159:

   .. table:: **Table 8** **alarm_actions** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                               |
      +=======================+=======================+===========================================================================+
      | type                  | String                | Specifies the alarm notification type.                                    |
      |                       |                       |                                                                           |
      |                       |                       | -  **notification**: indicates that a notification will be sent.          |
      |                       |                       | -  **autoscaling**: indicates that a scaling action will be triggered.    |
      +-----------------------+-----------------------+---------------------------------------------------------------------------+
      | notificationList      | Array of strings      | Specifies the list of objects to be notified if the alarm status changes. |
      |                       |                       |                                                                           |
      |                       |                       | .. note::                                                                 |
      |                       |                       |                                                                           |
      |                       |                       |    The IDs in the list are strings.                                       |
      +-----------------------+-----------------------+---------------------------------------------------------------------------+

   .. _ces_03_0027__table1819115871510:

   .. table:: **Table 9** **ok_actions** data structure description

      +-----------------------+-----------------------+------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                  |
      +=======================+=======================+==============================================================================+
      | type                  | String                | Specifies the notification type when an alarm is triggered.                  |
      |                       |                       |                                                                              |
      |                       |                       | -  **notification**: indicates that a notification will be sent.             |
      |                       |                       | -  **autoscaling**: indicates that a scaling action will be triggered.       |
      +-----------------------+-----------------------+------------------------------------------------------------------------------+
      | notificationList      | Array of strings      | Specifies the ID list of objects to be notified if the alarm status changes. |
      |                       |                       |                                                                              |
      |                       |                       | .. note::                                                                    |
      |                       |                       |                                                                              |
      |                       |                       |    The IDs in the list are strings.                                          |
      +-----------------------+-----------------------+------------------------------------------------------------------------------+

   .. _ces_03_0027__table1473091124015:

   .. table:: **Table 10** **condition** data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================================+
      | period                | Integer               | Specifies the interval (seconds) for checking whether the configured alarm rules are met.                                                                                                        |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | filter                | String                | Specifies the data rollup method. The following methods are supported:                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | -  **average**: Cloud Eye calculates the average value of metric data within a rollup period.                                                                                                    |
      |                       |                       | -  **max**: Cloud Eye calculates the maximum value of metric data within a rollup period.                                                                                                        |
      |                       |                       | -  **min**: Cloud Eye calculates the minimum value of metric data within a rollup period.                                                                                                        |
      |                       |                       | -  **sum**: Cloud Eye calculates the sum of metric data within a rollup period.                                                                                                                  |
      |                       |                       | -  **variance**: Cloud Eye calculates the variance value of metric data within a rollup period.                                                                                                  |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | comparison_operator   | String                | Specifies the alarm threshold operator, which can be **>**, **=**, **<**, **>=**, or **<=**.                                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value                 | Double                | Specifies the alarm threshold. Supported range: **0** to **Number. MAX_VALUE (1.7976931348623157e+108)**                                                                                         |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | For detailed thresholds, see the value range of each metric in the appendix. For example, you can set ECS **cpu_util** in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>` to **80**. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | unit                  | String                | Specifies the data unit. Enter up to 32 characters.                                                                                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | count                 | Integer               | Specifies the number of consecutive occurrence times that the alarm policy was met. Supported range: **1** to **5**                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0027__table1933614411408:

   .. table:: **Table 11** **meta_data** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                                                                           |
      +=======================+=======================+=======================================================================================================================================================================================================================================================================================+
      | count                 | Integer               | Specifies the number of returned results.                                                                                                                                                                                                                                             |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | marker                | String                | Specifies the pagination marker.                                                                                                                                                                                                                                                      |
      |                       |                       |                                                                                                                                                                                                                                                                                       |
      |                       |                       | For example, you have queried 10 records this time and **alarm_id** of the tenth record is **1441967036681YkazZ0deN**. In your next query, if **start** is set to **al1441967036681YkazZ0deN**, you can start your query from the next alarm rule ID of **al1441967036681YkazZ0deN**. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | total                 | Integer               | Specifies the total number of query results.                                                                                                                                                                                                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "metric_alarms": [
              {
                  "alarm_name": "alarm-ttttttt",
                  "alarm_description": "",
                  "metric": {
                      "namespace": "SYS.ECS",
                      "dimensions": [
                          {
                              "name": "instance_id",
                              "value": "07814c0e-59a1-4fcd-a6fb-56f2f6923046"
                          }
                      ],
                      "metric_name": "cpu_util"
                  },
                  "condition": {
                      "period": 300,
                      "filter": "average",
                      "comparison_operator": ">=",
                      "value": 0,
                      "unit": "%",
                      "count": 3
                  },
                  "alarm_enabled": true,
                  "alarm_level": 2,
                  "alarm_action_enabled": false,
                  "alarm_id": "al15330507498596W7vmlGKL",
                  "update_time": 1533050749992,
                  "alarm_state": "alarm"
              },
              {
                  "alarm_name": "alarm-m5rwxxxxxxx",
                  "alarm_description": "",
                  "metric": {
                      "namespace": "SYS.ECS",
                      "dimensions": [
                          {
                              "name": "instance_id",
                              "value": "30f3858d-4377-4514-9081-be5bdbf1392e"
                          }
                      ],
                      "metric_name": "network_incoming_bytes_aggregate_rate"
                  },
                  "condition": {
                      "period": 300,
                      "filter": "average",
                      "comparison_operator": ">=",
                      "value": 12,
                      "unit": "Byte/s",
                      "count": 3
                  },
                  "alarm_enabled": true,
                  "alarm_level": 2,
                  "alarm_action_enabled": true,
                  "alarm_actions": [
                      {
                          "type": "notification",
                          "notificationList": [
                              "urn:smn:region:68438a86d98e427e907e0097b7e35d48:test0315"
                          ]
                      }
                  ],
                  "ok_actions": [
                      {
                          "type": "notification",
                          "notificationList": [
                              "urn:smn:region:68438a86d98e427e907e0097b7e35d48:test0315"
                          ]
                      }
                  ],
                  "alarm_id": "al1533031226533nKJexAlbq",
                  "update_time": 1533204036276,
                  "alarm_state": "ok"
              }
          ],
          "meta_data": {
              "count": 2,
              "marker": "al1533031226533nKJexAlbq",
              "total": 389
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
   | 403 Forbidden             | You are forbidden to access the page requested.                      |
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
