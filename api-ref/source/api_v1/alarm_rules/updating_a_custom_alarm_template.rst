:original_name: ces_03_0066.html

.. _ces_03_0066:

Updating a Custom Alarm Template
================================

Function
--------

This API is used to update a custom alarm template.

URI
---

PUT /V1.0/{project_id}/alarm-template/{template_id}

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
      | template_id           | Yes                   | Specifies the ID of the custom alarm template you want to update.                                |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      PUT https://{Cloud Eye endpoint}/V1.0/{project_id}/alarm-template/{template_id}

Request
-------

-  Request parameters

   .. table:: **Table 2** Request parameters

      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter            | Mandatory       | Type             | Description                                                                                                                                                                |
      +======================+=================+==================+============================================================================================================================================================================+
      | template_name        | Yes             | String           | Specifies the name of the custom alarm template. The name can contain 1 to 128 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.             |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | template_description | No              | String           | Provides supplementary information about the custom alarm template. The description can contain 0 to 256 characters.                                                       |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | namespace            | Yes             | String           | Specifies the resource type selected for creating the custom alarm template, that is, the service namespace. For example, if you select ECS, **namespace** is **SYS.ECS**. |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimension_name       | Yes             | String           | Specifies the dimension corresponding to the resource type. If ECS is selected, the dimension is ECS and **dimension_name** is **instance_id**.                            |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | template_items       | Yes             | Array of objects | Specifies the alarm rules that you add to the custom alarm template. You can add up to 20 alarm rules.                                                                     |
      |                      |                 |                  |                                                                                                                                                                            |
      |                      |                 |                  | For details, see :ref:`Table 3 <ces_03_0066__table240293625811>`.                                                                                                          |
      +----------------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0066__table240293625811:

   .. table:: **Table 3** **template_items** data structure description

      +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type             | Description                                                                                             |
      +=================+=================+==================+=========================================================================================================+
      | metric_name     | Yes             | String           | Specifies the metric you add to the custom alarm template. For example, you can add ECS **cpu_util**.   |
      |                 |                 |                  |                                                                                                         |
      |                 |                 |                  | For the metric names of each resource, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------+
      | condition       | Yes             | Condition object | Specifies the alarm policy you created for the custom alarm template.                                   |
      |                 |                 |                  |                                                                                                         |
      |                 |                 |                  | For details, see :ref:`Table 4 <ces_03_0066__table6403153675817>`.                                      |
      +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------+
      | alarm_level     | No              | Integer          | Specifies the alarm severity.                                                                           |
      |                 |                 |                  |                                                                                                         |
      |                 |                 |                  | Possible severities are **1** (critical), **2** (major), **3** (minor), and **4** (informational).      |
      +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------+

   .. _ces_03_0066__table6403153675817:

   .. table:: **Table 4** **condition** data structure description

      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter           | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                  |
      +=====================+=================+=================+==============================================================================================================================================================================================================================================================================+
      | comparison_operator | Yes             | String          | Specifies the alarm threshold operator, which can be **>**, **=**, **<**, **>=**, **<=**, or **!=**.                                                                                                                                                                         |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | count               | Yes             | Integer         | Specifies the number of consecutive occurrence times that the alarm policy was met. Supported range: **1** to **5**                                                                                                                                                          |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | filter              | Yes             | String          | Specifies the data aggregation method. The value can be:                                                                                                                                                                                                                     |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | -  **average**: average value of metric data within an aggregation period.                                                                                                                                                                                                   |
      |                     |                 |                 | -  **max**: maximum value of metric data in an aggregation period.                                                                                                                                                                                                           |
      |                     |                 |                 | -  **min**: minimum value of metric data within an aggregation period.                                                                                                                                                                                                       |
      |                     |                 |                 | -  **sum**: sum of metric data within an aggregation period.                                                                                                                                                                                                                 |
      |                     |                 |                 | -  **variance**: variance value of metric data within an aggregation period.                                                                                                                                                                                                 |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | period              | Yes             | Integer         | Specifies how often Cloud Eye aggregates data.                                                                                                                                                                                                                               |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | The value can be:                                                                                                                                                                                                                                                            |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | -  **0**: Event alarms are triggered immediately.                                                                                                                                                                                                                            |
      |                     |                 |                 | -  **1**: Cloud Eye performs no aggregation and displays raw data.                                                                                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | -  **300**: Cloud Eye aggregates data every 5 minutes.                                                                                                                                                                                                                       |
      |                     |                 |                 | -  **1200**: Cloud Eye aggregates data every 20 minutes.                                                                                                                                                                                                                     |
      |                     |                 |                 | -  **3600**: Cloud Eye aggregates data every hour.                                                                                                                                                                                                                           |
      |                     |                 |                 | -  **14400**: Cloud Eye aggregates data every 4 hours.                                                                                                                                                                                                                       |
      |                     |                 |                 | -  **86400**: Cloud Eye aggregates data every 24 hours.                                                                                                                                                                                                                      |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | unit                | No              | String          | Specifies the data unit. The value can contain a maximum of 32 characters. You can set this parameter based on your service needs.                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | Minimum: **0**                                                                                                                                                                                                                                                               |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | Maximum: **32**                                                                                                                                                                                                                                                              |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value               | Yes             | Double          | Specifies the alarm threshold. Range: **0** to **Number. MAX_VALUE (1.7976931348623157e+108)** For detailed thresholds, see the value ranges of metrics in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. For example, you can set ECS **cpu_util** to **80**. |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | suppress_duration   | No              | Integer         | Specifies the interval for triggering an alarm if the alarm persists.                                                                                                                                                                                                        |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | Possible intervals are as follows:                                                                                                                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **0**: Cloud Eye triggers the alarm only once.                                                                                                                                                                                                                               |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **300**: Cloud Eye triggers the alarm every 5 minutes.                                                                                                                                                                                                                       |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **600**: Cloud Eye triggers the alarm every 10 minutes.                                                                                                                                                                                                                      |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **900**: Cloud Eye triggers the alarm every 15 minutes.                                                                                                                                                                                                                      |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **1800**: Cloud Eye triggers the alarm every 30 minutes.                                                                                                                                                                                                                     |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **3600**: Cloud Eye triggers the alarm every hour.                                                                                                                                                                                                                           |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **10800**: Cloud Eye triggers the alarm every 3 hours.                                                                                                                                                                                                                       |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **21600**: Cloud Eye triggers the alarm every 6 hours.                                                                                                                                                                                                                       |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **43200**: Cloud Eye triggers the alarm every 12 hours.                                                                                                                                                                                                                      |
      |                     |                 |                 |                                                                                                                                                                                                                                                                              |
      |                     |                 |                 | **86400**: Cloud Eye triggers the alarm every day.                                                                                                                                                                                                                           |
      +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      {
         "template_name": "alarmTemplate-Test01",
         "template_description": "Updating a custom alarm template",
         "namespace": "SYS.ECS",
         "dimension_name": "instance_id",
         "template_items": [
             {
                 "metric_name": "cpu_util",
                 "condition": {
                     "period": 1,
                     "filter": "average",
                     "comparison_operator": ">=",
                     "value": 90,
                     "unit": "%",
                     "count": 3,
                     "suppress_duration": 300
                 },
                 "alarm_level": 2
             },
             {
                 "metric_name": "mem_util",
                 "condition": {
                     "period": 1,
                     "filter": "average",
                     "comparison_operator": ">=",
                     "value": 90,
                     "unit": "%",
                     "count": 3,
                     "suppress_duration": 600
                 },
                 "alarm_level": 2
             }
         ]
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
   | Returned Values           | Description                                                          |
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
