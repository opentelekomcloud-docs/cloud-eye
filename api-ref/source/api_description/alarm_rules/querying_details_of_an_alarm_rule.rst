:original_name: ces_03_0028.html

.. _ces_03_0028:

Querying Details of an Alarm Rule
=================================

Function
--------

This API is used to query details of an alarm rule based on its ID.

URI
---

GET /V1.0/{project_id}/alarms/{alarm_id}

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

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/alarms/al1441967036681YkazZ0deN

Request
-------

None

Response
--------

-  Response parameters

   +-----------------------+-----------------------+--------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                        |
   +=======================+=======================+====================================================================+
   | metric_alarms         | Array of objects      | Specifies the list of alarm objects.                               |
   |                       |                       |                                                                    |
   |                       |                       | For details, see :ref:`Table 2 <ces_03_0028__table1358574011306>`. |
   +-----------------------+-----------------------+--------------------------------------------------------------------+

   .. _ces_03_0028__table1358574011306:

   .. table:: **Table 2** **metric_alarms** data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                            |
      +=======================+=======================+========================================================================================================================================================+
      | alarm_name            | String                | Specifies the alarm rule name.                                                                                                                         |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_description     | String                | Provides supplementary information about the alarm rule.                                                                                               |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric                | Object                | Specifies the alarm metric.                                                                                                                            |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 3 <ces_03_0028__table1358724013016>`.                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | condition             | Object                | Specifies the alarm triggering condition.                                                                                                              |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 7 <ces_03_0028__table159417407300>`.                                                                                      |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_enabled         | Boolean               | Specifies whether to enable the alarm rule.                                                                                                            |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_level           | Integer               | Specifies the alarm severity, which can be **1**, **2** (default), **3** or **4**, indicating critical, major, minor, and informational, respectively. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_action_enabled  | Boolean               | Specifies whether to enable the action to be triggered by an alarm.                                                                                    |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_actions         | Array of objects      | Specifies the action to be triggered by an alarm.                                                                                                      |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 5 <ces_03_0028__table359064073020>`.                                                                                      |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ok_actions            | Array of objects      | Specifies the action to be triggered after the alarm is cleared.                                                                                       |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 6 <ces_03_0028__table1859144073012>`.                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_id              | String                | Specifies the alarm rule ID.                                                                                                                           |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | update_time           | Long                  | Specifies when the alarm status changed. The time is a UNIX timestamp and the unit is ms.                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_state           | String                | Specifies the alarm status, which can be                                                                                                               |
      |                       |                       |                                                                                                                                                        |
      |                       |                       | -  **ok**: The alarm status is normal.                                                                                                                 |
      |                       |                       | -  **alarm**: An alarm is generated.                                                                                                                   |
      |                       |                       | -  **insufficient_data**: The required data is insufficient.                                                                                           |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0028__table1358724013016:

   .. table:: **Table 3** **metric** data structure description

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                           |
      +=======================+=======================+=======================================================================================================================================================================================================+
      | namespace             | String                | Specifies the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions            | Array of objects      | Specifies the list of metric dimensions.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                       |
      |                       |                       | For details, see :ref:`Table 4 <ces_03_0028__table15589124016303>`.                                                                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name           | String                | Specifies the metric ID. For example, if the monitoring metric of an ECS is CPU usage, **metric_name** is **cpu_util**. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0028__table15589124016303:

   .. table:: **Table 4** **dimensions** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================+
      | name                  | String                | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value                 | String                | Specifies the dimension value, for example, an ECS ID.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                     |
      |                       |                       | Enter 1 to 256 characters.                                                                                                                                                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0028__table359064073020:

   .. table:: **Table 5** **alarm_actions** data structure description

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

   .. _ces_03_0028__table1859144073012:

   .. table:: **Table 6** **ok_actions** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                               |
      +=======================+=======================+===========================================================================+
      | type                  | String                | Specifies the notification type when an alarm is triggered.               |
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

   .. _ces_03_0028__table159417407300:

   .. table:: **Table 7** **condition** data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================================+
      | period                | Integer               | Specifies the interval (seconds) for checking whether the configured alarm rules are met.                                                                                                        |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | filter                | String                | Specifies the data rollup method, which can be                                                                                                                                                   |
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
      | suppress_duration     | Integer               | Specifies the interval for triggering an alarm if the alarm persists.                                                                                                                            |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | Possible intervals are as follows:                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **0**: Cloud Eye triggers the alarm only once.                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **300**: Cloud Eye triggers the alarm every 5 minutes.                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **600**: Cloud Eye triggers the alarm every 10 minutes.                                                                                                                                          |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **900**: Cloud Eye triggers the alarm every 15 minutes.                                                                                                                                          |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **1800**: Cloud Eye triggers the alarm every 30 minutes.                                                                                                                                         |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **3600**: Cloud Eye triggers the alarm every hour.                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **10800**: Cloud Eye triggers the alarm every 3 hours.                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **21600**: Cloud Eye triggers the alarm every 6 hours.                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **43200**: Cloud Eye triggers the alarm every 12 hours.                                                                                                                                          |
      |                       |                       |                                                                                                                                                                                                  |
      |                       |                       | **86400**: Cloud Eye triggers the alarm every day.                                                                                                                                               |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
      "metric_alarms":
        [
         {
          "alarm_name":"alarm-ipwx",
          "alarm_description":"",
          "metric":
           {
            "namespace":"SYS.ELB",
            "dimensions":
            [
             {
              "name":"lb_instance_id",
              "value":"44d06d10-bce0-4237-86b9-7b4d1e7d5621"
             }
            ],
            "metric_name":"m8_out_Bps"
            },
          "condition":
           {
            "period":300,
            "filter":"sum",
            "comparison_operator":">=",
            "value":0,
            "unit":"",
            "count":1,
            "suppress_duration":1800
            },
          "alarm_enabled":true,
          "alarm_level": 2,
          "alarm_action_enabled":true,
          "alarm_actions":
           [
            {
             "type":"notification",
             "notificationList":["urn:smn:region:68438a86d98e427e907e0097b7e35d48:sd"]
            }
           ],
          "ok_actions":
           [
            {
             "type":"notification",
             "notificationList":["urn:smn:region:68438a86d98e427e907e0097b7e35d48:sd"]
            }
           ],
          "alarm_id":"al1498096535573r8DNy7Gyk",
          "update_time":1498100100000,
          "alarm_state":"alarm"
         }
        ]
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
