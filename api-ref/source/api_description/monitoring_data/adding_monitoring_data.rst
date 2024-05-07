:original_name: en-us_topic_0032831274.html

.. _en-us_topic_0032831274:

Adding Monitoring Data
======================

Function
--------

This API is used to add one or more pieces of custom metric monitoring data to solve the problem that the system metrics cannot meet specific service requirements.

URI
---

POST /V1.0/{project_id}/metric-data

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

Request
-------

.. important::

   #. The size of a POST request cannot exceed 512 KB. Otherwise, the request will be denied.
   #. The period for sending POST requests must be shorter than the minimum aggregation period. Otherwise, the aggregated data will be noncontinuous. For example, if the aggregation period is 5 minutes and the POST request sending period is 7 minutes, the data will be aggregated every 10 minutes, rather than 5 minutes.
   #. Timestamp (collect_time) in the POST request body value must be within the period that starts from three days before the current time to 10 minutes after the current time. If it is not in this range, you are not allowed to insert the metric data.

-  Request parameters

   .. table:: **Table 2** Parameter description

      +-----------------+------------------+-----------------+--------------------------------------------------------------------------------+
      | Parameter       | Type             | Mandatory       | Description                                                                    |
      +=================+==================+=================+================================================================================+
      | Array elements  | Array of objects | Yes             | Specifies whether to add one or more pieces of custom metric monitoring data.  |
      |                 |                  |                 |                                                                                |
      |                 |                  |                 | For details, see :ref:`Table 3 <en-us_topic_0032831274__table15597145972912>`. |
      +-----------------+------------------+-----------------+--------------------------------------------------------------------------------+

   .. _en-us_topic_0032831274__table15597145972912:

   .. table:: **Table 3** Array elements

      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                  |
      +=================+=================+=================+==============================================================================================================================================================================================================================================================================================================================================+
      | metric          | Yes             | Object          | Specifies the metric data.                                                                                                                                                                                                                                                                                                                   |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | For details, see :ref:`Table 4 <en-us_topic_0032831274__table25981459182914>`.                                                                                                                                                                                                                                                               |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ttl             | Yes             | Integer         | Specifies the data validity period. The unit is second.                                                                                                                                                                                                                                                                                      |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | Supported range: 1 to 604800                                                                                                                                                                                                                                                                                                                 |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | If the validity period expires, the data will be automatically deleted.                                                                                                                                                                                                                                                                      |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | collect_time    | Yes             | Long            | Specifies when the data was collected.                                                                                                                                                                                                                                                                                                       |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | The time is UNIX timestamp (ms) format.                                                                                                                                                                                                                                                                                                      |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | .. note::                                                                                                                                                                                                                                                                                                                                    |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 |    Since there is a latency between the client and the server, the data timestamp to be inserted should be within the period that starts from three days before the current time plus 20s to 10 minutes after the current time minus 20s. In this way, the timestamp will be inserted to the database without being affected by the latency. |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value           | Yes             | Double          | Specifies the monitoring metric data to be added, which can be an integer or a floating point number.                                                                                                                                                                                                                                        |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | unit            | No              | String          | Specifies the data unit.                                                                                                                                                                                                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | Enter a maximum of 32 characters.                                                                                                                                                                                                                                                                                                            |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | type            | No              | String          | Specifies the enumerated type.                                                                                                                                                                                                                                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | Possible types:                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                 | -  **int**                                                                                                                                                                                                                                                                                                                                   |
      |                 |                 |                 | -  **float**                                                                                                                                                                                                                                                                                                                                 |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0032831274__table25981459182914:

   .. table:: **Table 4** **metric** data structure description

      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                                                                                                                 |
      +=================+=================+==================+=============================================================================================================================================================================================================================================================================================================================================================================+
      | namespace       | Yes             | String           | Specifies the customized namespace. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                                                                                                                                                                                           |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                             |
      |                 |                 |                  | The namespace must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_). In addition, **service** cannot start with **SYS**, **AGT**, or **SRE**, and **namespace** cannot be **SERVICE.BMS** because this namespace has been used by the system. |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                             |
      |                 |                 |                  | You can leave this parameter blank when you set **alarm_type** to **(EVENT.SYS\| EVENT.CUSTOM)**.                                                                                                                                                                                                                                                                           |
      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions      | Yes             | Array of objects | Specifies the metric dimension. A maximum of three dimensions are supported.                                                                                                                                                                                                                                                                                                |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                             |
      |                 |                 |                  | For details, see :ref:`Table 5 <en-us_topic_0032831274__table17598459112913>`.                                                                                                                                                                                                                                                                                              |
      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name     | Yes             | String           | Specifies the metric ID. For example, if the monitoring metric of an ECS is CPU usage, **metric_name** is **cpu_util**. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                                                                                                       |
      +-----------------+-----------------+------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _en-us_topic_0032831274__table17598459112913:

   .. table:: **Table 5** **dimensions** data structure description

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

-  Example request

   Example request 1: Add **cpu_util** data of a custom dimension. The instance ID is **6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d**.

   .. code-block::

      [
          {
              "metric": {
                  "namespace": "MINE.APP",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
              "ttl": 172800,
              "collect_time": 1463598260000,
              "type": "float",
              "value": 0.09,
              "unit": "%"
          },
          {
              "metric": {
                  "namespace": "MINE.APP",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
              "ttl": 172800,
              "collect_time": 1463598270000,
              "type": "float",
              "value": 0.12,
              "unit": "%"
          }
      ]

   Example request 2: Add **rds021_myisam_buf_usage** data of the RDS instance whose **rds_cluster_id** is **3c8cc15614ab46f5b8743317555e0de2in01**.

   .. code-block::

      [
          {
              "metric": {
                  "namespace": "SYS.RDS",
                  "dimensions": [
                      {
                          "name": "rds_cluster_id",
                          "value": "3c8cc15614ab46f5b8743317555e0de2in01"
                      }
                  ],
                  "metric_name": "rds021_myisam_buf_usage"
              },
              "ttl": 172800,
              "collect_time": 1463598260000,
              "type": "float",
              "value": 0.01,
              "unit": "Ratio"
          }
      ]

Response
--------

The response has no message body.

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
