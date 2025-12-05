:original_name: ces_03_0069.html

.. _ces_03_0069:

Modifying an Alarm Rule
=======================

Function
--------

This API is used to modify an alarm rule.

URI
---

PUT /V1.0/{project_id}/alarms/{alarm_id}

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      |                       |                       |                                                                                                  |
      |                       |                       | Minimum: **1**                                                                                   |
      |                       |                       |                                                                                                  |
      |                       |                       | Maximum: **64**                                                                                  |
      |                       |                       |                                                                                                  |
      |                       |                       | **Regular expression matching**: ^[a-zA-Z0-9-]{1,64}$                                            |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | alarm_id              | Yes                   | Specifies the alarm rule ID.                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      PUT https://{Cloud Eye endpoint}/V1.0/{project_id}/alarms/{alarm_id}

Request
-------

-  Request parameters

   .. table:: **Table 2** Parameter description

      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter            | Mandatory       | Type             | Description                                                                                                                                                                                                    |
      +======================+=================+==================+================================================================================================================================================================================================================+
      | alarm_name           | No              | String           | Specifies the alarm rule name. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                             |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_description    | No              | String           | Provides supplementary information about the alarm rule. Enter 0 to 256 characters.                                                                                                                            |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | condition            | No              | Condition object | Specifies the alarm policy set in the alarm rule.                                                                                                                                                              |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | For details, see :ref:`Table 3 <ces_03_0069__table159417407300>`.                                                                                                                                              |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_action_enabled | No              | Boolean          | Specifies whether to enable the action to be triggered by an alarm. The default value is **true**.                                                                                                             |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | .. note::                                                                                                                                                                                                      |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  |    If you set **alarm_action_enabled** to **true**, you must specify either **alarm_actions** or **ok_actions**. If **alarm_actions** and **ok_actions** coexist, their **notificationList** must be the same. |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_level          | No              | Integer          | Specifies the alarm severity, which can be **1**, **2** (default), **3** or **4**, indicating critical, major, minor, and informational, respectively.                                                         |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_type           | No              | String           | Specifies the alarm rule type. The value cannot be changed and must be the same as the alarm type of the current alarm rule.                                                                                   |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alarm_actions        | No              | Array of objects | Specifies the action to be triggered by an alarm. The structure is as follows: { "type": "notification","notificationList": ["urn:smn:southchina:68438a86d98e427e907e0097b7e35d47:sd"] }                       |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | Possible values of **type** are as follows:                                                                                                                                                                    |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | **notification**: A notification will be sent.                                                                                                                                                                 |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | **autoscaling**: A scaling action will be triggered.                                                                                                                                                           |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | For details, see :ref:`Table 4 <ces_03_0069__table359064073020>`.                                                                                                                                              |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ok_actions           | No              | Array of objects | Specifies the action to be triggered after the alarm is cleared.                                                                                                                                               |
      |                      |                 |                  |                                                                                                                                                                                                                |
      |                      |                 |                  | For details, see :ref:`Table 5 <ces_03_0069__table1859144073012>`.                                                                                                                                             |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0069__table159417407300:

   .. table:: **Table 3** **condition** data structure description

      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter           | Mandatory       | Type            | Description                                                                                                                        |
      +=====================+=================+=================+====================================================================================================================================+
      | period              | Yes             | Integer         | Specifies how often Cloud Eye aggregates data, which can be                                                                        |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | -  **0**: Event alarms are triggered immediately.                                                                                  |
      |                     |                 |                 | -  **1**: Cloud Eye performs no aggregation and displays raw data.                                                                 |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | -  **300**: Cloud Eye aggregates data every 5 minutes.                                                                             |
      |                     |                 |                 | -  **1200**: Cloud Eye aggregates data every 20 minutes.                                                                           |
      |                     |                 |                 | -  **3600**: Cloud Eye aggregates data every hour.                                                                                 |
      |                     |                 |                 | -  **14400**: Cloud Eye aggregates data every 4 hours.                                                                             |
      |                     |                 |                 | -  **86400**: Cloud Eye aggregates data every 24 hours.                                                                            |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | filter              | Yes             | String          | Specifies the data aggregation method. The value can be:                                                                           |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | -  **average**: average value of metric data within an aggregation period.                                                         |
      |                     |                 |                 | -  **max**: maximum value of metric data in an aggregation period.                                                                 |
      |                     |                 |                 | -  **min**: minimum value of metric data within an aggregation period.                                                             |
      |                     |                 |                 | -  **sum**: sum of metric data within an aggregation period.                                                                       |
      |                     |                 |                 | -  **variance**: variance value of metric data within an aggregation period.                                                       |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | comparison_operator | Yes             | String          | Specifies the alarm threshold operator, which can be **>**, **=**, **<**, **>=**, **<=**, or **!=**.                               |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | value               | Yes             | Double          | Specifies the alarm threshold.                                                                                                     |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | Supported range: **0** to **Number. MAX_VALUE (1.7976931348623157e+108)**                                                          |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | For detailed thresholds, see the value range of each metric in the appendix. For example, you can set ECS **cpu_util** to **80**.  |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | unit                | No              | String          | Specifies the data unit. The value can contain a maximum of 32 characters. You can set this parameter based on your service needs. |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | Minimum: **0**                                                                                                                     |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | Maximum: **32**                                                                                                                    |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | count               | Yes             | Integer         | Specifies the number of consecutive occurrence times that the alarm policy was met. Supported range: **1** to **5**                |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+
      | suppress_duration   | No              | Integer         | Specifies the interval for triggering an alarm if the alarm persists. Possible intervals are as follows:                           |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **0**: Cloud Eye triggers the alarm only once.                                                                                     |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **300**: Cloud Eye triggers the alarm every 5 minutes.                                                                             |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **600**: Cloud Eye triggers the alarm every 10 minutes.                                                                            |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **900**: Cloud Eye triggers the alarm every 15 minutes.                                                                            |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **1800**: Cloud Eye triggers the alarm every 30 minutes.                                                                           |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **3600**: Cloud Eye triggers the alarm every hour.                                                                                 |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **10800**: Cloud Eye triggers the alarm every 3 hours.                                                                             |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **21600**: Cloud Eye triggers the alarm every 6 hours.                                                                             |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **43200**: Cloud Eye triggers the alarm every 12 hours.                                                                            |
      |                     |                 |                 |                                                                                                                                    |
      |                     |                 |                 | **86400**: Cloud Eye triggers the alarm every day.                                                                                 |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0069__table359064073020:

   .. table:: **Table 4** **alarm_actions** data structure description

      +------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter        | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                      |
      +==================+=================+==================+==================================================================================================================================================================================================================================================================================+
      | type             | Yes             | String           | Specifies the alarm notification type.                                                                                                                                                                                                                                           |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                  |
      |                  |                 |                  | -  **notification**: A notification will be sent.                                                                                                                                                                                                                                |
      |                  |                 |                  | -  **autoscaling**: A scaling action will be triggered.                                                                                                                                                                                                                          |
      +------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | notificationList | Yes             | Array of strings | Specifies the list of objects to be notified of alarm status changes. You can add up to 5 object IDs. You can obtain the **topicUrn** value from SMN in the following format: ``urn:smn:([a-z]|[A-Z]|[0-9]|\-){1,32}:([a-z]|[A-Z]|[0-9]){32}:([a-z]|[A-Z]|[0-9]|\-|\_){1,256}``. |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                  |
      |                  |                 |                  | If you set **type** to **notification**, you must specify **notificationList**. If you set **type** to **autoscaling**, you must set **notificationList** to **[]**.                                                                                                             |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                  |
      |                  |                 |                  | .. note::                                                                                                                                                                                                                                                                        |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                  |
      |                  |                 |                  |    -  To make the AS alarm rules take effect, you must bind scaling policies. For details, see the *Auto Scaling API Reference*.                                                                                                                                                 |
      |                  |                 |                  |    -  If you set **alarm_action_enabled** to **true**, you must specify either **alarm_actions** or **ok_actions**.                                                                                                                                                              |
      |                  |                 |                  |    -  If **alarm_actions** and **ok_actions** coexist, their **notificationList** must be the same.                                                                                                                                                                              |
      |                  |                 |                  |    -  The IDs in the list are strings.                                                                                                                                                                                                                                           |
      +------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0069__table1859144073012:

   .. table:: **Table 5** **ok_actions** data structure description

      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter        | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                          |
      +==================+=================+==================+======================================================================================================================================================================================================================================================================================+
      | type             | Yes             | String           | Specifies the notification type when an alarm is triggered.                                                                                                                                                                                                                          |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | -  **notification**: A notification will be sent.                                                                                                                                                                                                                                    |
      |                  |                 |                  | -  **autoscaling**: A scaling action will be triggered.                                                                                                                                                                                                                              |
      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | notificationList | Yes             | Array of objects | Specifies the list of objects to be notified if the alarm status changes. You can add up to 5 object IDs. You can obtain the **topicUrn** value from SMN in the following format: ``urn:smn:([a-z]|[A-Z]|[0-9]|\-){1,32}:([a-z]|[A-Z]|[0-9]){32}:([a-z]|[A-Z]|[0-9]|\-|\_){1,256}``. |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  | .. note::                                                                                                                                                                                                                                                                            |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  |    If you set **alarm_action_enabled** to **true**, you must specify either **alarm_actions** or **ok_actions**.                                                                                                                                                                     |
      |                  |                 |                  |                                                                                                                                                                                                                                                                                      |
      |                  |                 |                  |    If **alarm_actions** and **ok_actions** coexist, their **notificationList** must be the same.                                                                                                                                                                                     |
      +------------------+-----------------+------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      {
         "alarm_name": "alarm-update-test01",
         "alarm_description": "alarm-update-test01",
         "condition": {
             "comparison_operator": ">=",
             "count": 3,
             "filter": "average",
             "period": 1,
             "value": 95
         },
         "alarm_action_enabled": false,
         "alarm_level": 2
      }

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
