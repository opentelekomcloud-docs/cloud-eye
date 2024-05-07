:original_name: ces_03_0031.html

.. _ces_03_0031:

Creating an Alarm Rule
======================

Function
--------

This API is used to create an alarm rule.

URI
---

POST /V1.0/{project_id}/alarms

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

      POST https://{Cloud Eye endpoint}/V1.0/{project_id}/alarms

Request
-------

-  Request parameters

   .. table:: **Table 2** Request parameters

      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter            | Mandatory       | Type             | Description                                                                                                                                                                                            |
      +======================+=================+==================+========================================================================================================================================================================================================+
      | alarm_name           | Yes             | String           | Specifies the alarm rule name.                                                                                                                                                                         |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | Enter 1 to 128 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                         |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_description    | No              | String           | Provides supplementary information about the alarm rule. Enter 0 to 256 characters.                                                                                                                    |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric               | Yes             | Object           | Specifies the alarm metric.                                                                                                                                                                            |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | For details, see :ref:`Table 3 <ces_03_0031__table1358724013016>`.                                                                                                                                     |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | condition            | Yes             | Object           | Specifies the alarm triggering condition.                                                                                                                                                              |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | For details, see :ref:`Table 7 <ces_03_0031__table159417407300>`.                                                                                                                                      |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_enabled        | No              | Boolean          | Specifies whether to enable the alarm.                                                                                                                                                                 |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | The default value is **true**.                                                                                                                                                                         |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_action_enabled | No              | Boolean          | Specifies whether to enable the action to be triggered by an alarm. The default value is **true**.                                                                                                     |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | .. note::                                                                                                                                                                                              |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  |    If you set **alarm_action_enabled** to **true**, you must specify either **alarm_actions** or **ok_actions**. (You do not need to configure the deprecated parameter **insufficientdata_actions**.) |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  |    If **alarm_actions** and **ok_actions** coexist, their **notificationList** must be the same. (You do not need to configure the deprecated parameter **insufficientdata_actions**.)                 |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_level          | No              | Integer          | Specifies the alarm severity, which can be **1**, **2** (default), **3** or **4**, indicating critical, major, minor, and informational, respectively.                                                 |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_type           | No              | String           | Specifies the alarm rule type.                                                                                                                                                                         |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | **EVENT.SYS**: The alarm rule is created for system events. **EVENT.CUSTOM**: The alarm rule is created for custom events.                                                                             |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_actions        | No              | Array of objects | Specifies the action to be triggered by an alarm.                                                                                                                                                      |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | An example structure is as follows:                                                                                                                                                                    |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | {                                                                                                                                                                                                      |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | "type": "notification","notificationList": ["urn:smn:region:68438a86d98e427e907e0097b7e35d47:sd"]                                                                                                      |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | }                                                                                                                                                                                                      |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | For details, see :ref:`Table 5 <ces_03_0031__table359064073020>`.                                                                                                                                      |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ok_actions           | No              | Array of objects | Specifies the action to be triggered after the alarm is cleared.                                                                                                                                       |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | Its structure is:                                                                                                                                                                                      |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | { "type": "notification","notificationList": ["urn:smn:region:68438a86d98e427e907e0097b7e35d47:sd"] }                                                                                                  |
      |                      |                 |                  |                                                                                                                                                                                                        |
      |                      |                 |                  | For details, see :ref:`Table 6 <ces_03_0031__table1859144073012>`.                                                                                                                                     |
      +----------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0031__table1358724013016:

   .. table:: **Table 3** **metric** data structure description

      +-------------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter         | Mandatory       | Type             | Description                                                                                                                                                                                           |
      +===================+=================+==================+=======================================================================================================================================================================================================+
      | namespace         | Yes             | String           | Specifies the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                   |
      |                   |                 |                  |                                                                                                                                                                                                       |
      |                   |                 |                  | The namespace must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_).    |
      +-------------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions        | No              | Array of objects | Specifies the metric dimension list. When **resource_group_id** is not used, **dimensions** is mandatory.                                                                                             |
      |                   |                 |                  |                                                                                                                                                                                                       |
      |                   |                 |                  | For details, see :ref:`Table 4 <ces_03_0031__table15589124016303>`.                                                                                                                                   |
      +-------------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name       | Yes             | String           | Specifies the metric name.                                                                                                                                                                            |
      |                   |                 |                  |                                                                                                                                                                                                       |
      |                   |                 |                  | Start with a letter. Enter 1 to 64 characters. Only letters, digits, and underscores (_) are allowed.                                                                                                 |
      |                   |                 |                  |                                                                                                                                                                                                       |
      |                   |                 |                  | For details, see the metric name queried in :ref:`Querying Metrics <ces_03_0023>`.                                                                                                                    |
      +-------------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_group_id | No              | String           | Specifies the resource group ID selected during the alarm rule creation, for example, **rg1603786526428bWbVmk4rP**.                                                                                   |
      |                   |                 |                  |                                                                                                                                                                                                       |
      |                   |                 |                  | .. note::                                                                                                                                                                                             |
      |                   |                 |                  |                                                                                                                                                                                                       |
      |                   |                 |                  |    If you create alarm rules for resource groups, you must specify **resource_group_id** and **name**, enter at least one dimension for **dimensions**, and set **alarm_type** to **RESOURCE_GROUP**. |
      +-------------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0031__table15589124016303:

   .. table:: **Table 4** **dimensions** data structure description

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                         |
      +=================+=================+=================+=====================================================================================================================================================================================================================+
      | name            | Yes             | String          | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 | Start with a letter. Enter 1 to 32 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                  |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value           | Yes             | String          | Specifies the dimension value, for example, an ECS ID.                                                                                                                                                              |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 | Start with a letter or a digit. Enter 1 to 256 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                      |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0031__table359064073020:

   .. table:: **Table 5** **alarm_actions** data structure description

      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter        | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                          |
      +==================+=================+==================+======================================================================================================================================================================================================================================================================================+
      | type             | Yes             | String           | Specifies the alarm notification type.                                                                                                                                                                                                                                               |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | -  **notification**: indicates that a notification will be sent.                                                                                                                                                                                                                     |
      |                  |                 |                  | -  **autoscaling**: indicates that a scaling action will be triggered.                                                                                                                                                                                                               |
      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | notificationList | Yes             | Array of strings | Specifies the list of objects to be notified if the alarm status changes. You can add up to 5 object IDs. You can obtain the **topicUrn** value from SMN in the following format: ``urn:smn:([a-z]|[A-Z]|[0-9]|\-){1,32}:([a-z]|[A-Z]|[0-9]){32}:([a-z]|[A-Z]|[0-9]|\-|\_){1,256}``. |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | If you set **type** to **notification**, you must specify **notificationList**. If you set **type** to **autoscaling**, you must set **notificationList** to **[]**.                                                                                                                 |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | .. note::                                                                                                                                                                                                                                                                            |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  |    -  To make the AS alarm rules take effect, you must bind scaling policies. For details, see the *Auto Scaling API Reference*.                                                                                                                                                     |
      |                  |                 |                  |    -  If you set **alarm_action_enabled** to **true**, you must specify either **alarm_actions** or **ok_actions**. (You do not need to configure the deprecated parameter **insufficientdata_actions**.)                                                                            |
      |                  |                 |                  |    -  If **alarm_actions** and **ok_actions** coexist, their **notificationList** must be the same. (You do not need to configure the deprecated parameter **insufficientdata_actions**.)                                                                                            |
      |                  |                 |                  |    -  The IDs in the list are strings.                                                                                                                                                                                                                                               |
      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0031__table1859144073012:

   .. table:: **Table 6** **ok_actions** data structure description

      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter        | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                          |
      +==================+=================+==================+======================================================================================================================================================================================================================================================================================+
      | type             | Yes             | String           | Specifies the notification type when an alarm is triggered.                                                                                                                                                                                                                          |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | -  **notification**: indicates that a notification will be sent.                                                                                                                                                                                                                     |
      |                  |                 |                  | -  **autoscaling**: indicates that a scaling action will be triggered.                                                                                                                                                                                                               |
      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | notificationList | Yes             | Array of objects | Specifies the list of objects to be notified if the alarm status changes. You can add up to 5 object IDs. You can obtain the **topicUrn** value from SMN in the following format: ``urn:smn:([a-z]|[A-Z]|[0-9]|\-){1,32}:([a-z]|[A-Z]|[0-9]){32}:([a-z]|[A-Z]|[0-9]|\-|\_){1,256}``. |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | .. note::                                                                                                                                                                                                                                                                            |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  |    If you set **alarm_action_enabled** to **true**, you must specify either **alarm_actions** or **ok_actions**. (You do not need to configure the deprecated parameter **insufficientdata_actions**.)                                                                               |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  |    If **alarm_actions** and **ok_actions** coexist, their **notificationList** must be the same. (You do not need to configure the deprecated parameter **insufficientdata_actions**.)                                                                                               |
      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0031__table159417407300:

   .. table:: **Table 7** **condition** data structure description

      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter           | Mandatory       | Type            | Description                                                                                                                                                                                      |
      +=====================+=================+=================+==================================================================================================================================================================================================+
      | period              | Yes             | Integer         | Specifies the period during which Cloud Eye determines whether to trigger an alarm. Unit: second                                                                                                 |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | Possible periods are **1**, **300**, **1200**, **3600**, **14400**, and **86400**.                                                                                                               |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | .. note::                                                                                                                                                                                        |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 |    -  If you set **period** to **1**, Cloud Eye uses raw data to determine whether to trigger an alarm.                                                                                          |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | filter              | Yes             | String          | Specifies the data rollup method.                                                                                                                                                                |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | Possible methods are **max**, **min**, **average**, **sum**, or **variance**.                                                                                                                    |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | comparison_operator | Yes             | String          | Specifies the alarm threshold operator.                                                                                                                                                          |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | Possible operators are **>**, **=**, **<**, **>=**, and **<=**.                                                                                                                                  |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value               | Yes             | Double          | Specifies the alarm threshold.                                                                                                                                                                   |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | Supported range: **0** to **Number. MAX_VALUE (1.7976931348623157e+108)**                                                                                                                        |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | For detailed thresholds, see the value range of each metric in the appendix. For example, you can set ECS **cpu_util** in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>` to **80**. |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | unit                | No              | String          | Specifies the data unit. Enter up to 32 characters.                                                                                                                                              |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | count               | Yes             | Integer         | Specifies the number of consecutive occurrence times that the alarm policy was met. Supported range: **1** to **5**                                                                              |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | suppress_duration   | No              | Integer         | Specifies the interval for triggering an alarm if the alarm persists.                                                                                                                            |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | Possible intervals are as follows:                                                                                                                                                               |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **0**: Cloud Eye triggers the alarm only once.                                                                                                                                                   |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **300**: Cloud Eye triggers the alarm every 5 minutes.                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **600**: Cloud Eye triggers the alarm every 10 minutes.                                                                                                                                          |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **900**: Cloud Eye triggers the alarm every 15 minutes.                                                                                                                                          |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **1800**: Cloud Eye triggers the alarm every 30 minutes.                                                                                                                                         |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **3600**: Cloud Eye triggers the alarm every hour.                                                                                                                                               |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **10800**: Cloud Eye triggers the alarm every 3 hours.                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **21600**: Cloud Eye triggers the alarm every 6 hours.                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **43200**: Cloud Eye triggers the alarm every 12 hours.                                                                                                                                          |
      |                     |                 |                 |                                                                                                                                                                                                  |
      |                     |                 |                 | **86400**: Cloud Eye triggers the alarm every day.                                                                                                                                               |
      +---------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request 1

   Creating an alarm rule to monitor a metric

   .. code-block::

      {
          "alarm_name": "alarm-rp0E",
          "alarm_description": "",
          "metric": {
              "namespace": "SYS.ECS",
              "dimensions": [
                  {
                      "name": "instance_id",
                      "value": "33328f02-3814-422e-b688-bfdba93d4051"
                  }
              ],
              "metric_name": "network_outgoing_bytes_rate_inband"
          },
          "condition": {
              "period": 300,
              "filter": "average",
              "comparison_operator": ">=",
              "value": 6,
              "unit": "Byte/s",
              "count": 1
         },
          "alarm_enabled": true,
          "alarm_action_enabled": true,
          "alarm_level": 2,
          "alarm_actions": [
              {
                  "type": "notification",
                  "notificationList": ["urn:smn:region:68438a86d98e427e907e0097b7e35d48:sd"]
              }
          ],
          "ok_actions": [
              {
                  "type": "notification",
                  "notificationList": ["urn:smn:region:68438a86d98e427e907e0097b7e35d48:sd"]
              }
          ]
      }

-  Example request 2

   Creating an alarm rule to monitor an event

   .. code-block::

      {
       "alarm_name": "alarm-test",
       "metric": {
        "namespace": "SYS.ECS",
        "metric_name": "instance_resize_scheduled",
        "dimensions": [
         {
          "name": "instance_id",
          "value": "d53692e5-828b-495b-a5e2-a1b227f6034c"
         }
        ]
       },
       "condition": {
        "comparison_operator": ">=",
        "count": 1,
        "filter": "average",
        "period": 0,
        "unit": "count",
        "value": 1
       },
       "alarm_enabled": true,
       "alarm_action_enabled": true,
       "alarm_level": 2,
       "alarm_type": "EVENT.SYS",
       "alarm_actions": [
        {
         "type": "notification",
         "notificationList": ["urn:smn:region:ce8476c174f94c6991ea7885e3380d99:sd"]
        }
       ],
       "ok_actions": [
        {
         "type": "notification",
         "notificationList": ["urn:smn:region:ce8476c174f94c6991ea7885e3380d99:sd"]
        }
       ]
      }

Response
--------

-  Response parameters

   .. table:: **Table 8** Response parameters

      ========= ====== ============================
      Parameter Type   Description
      ========= ====== ============================
      alarm_id  String Specifies the alarm rule ID.
      ========= ====== ============================

-  Example response

   .. code-block::

      {
          "alarm_id":"al1450321795427dR8p5mQBo"
      }

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
