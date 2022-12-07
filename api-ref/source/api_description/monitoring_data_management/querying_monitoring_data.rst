:original_name: ces_03_0033.html

.. _ces_03_0033:

Querying Monitoring Data
========================

Function
--------

This API is used to query the monitoring data at a specified granularity for a specified metric in a specified period of time. You can specify the dimension of data to be queried.

URI
---

GET /V1.0/{project_id}/metric-data?namespace={namespace}&metric_name={metric_name}&dim.{i}=key,value&from={from}&to={to}&period={period}&filter={filter}

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

   .. table:: **Table 2** Query parameter description

      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                   |
      +=================+=================+=================+===============================================================================================================================================================================================================================================================================+
      | namespace       | Yes             | String          | Specifies the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                                                                                           |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | The namespace must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_).                                                                            |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name     | Yes             | String          | Specifies the metric name. You can obtain the metric names of existing alarm rules by referring to :ref:`Querying Metrics <ces_03_0023>`.                                                                                                                                     |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | from            | Yes             | String          | Specifies the start time of the query. The time is a UNIX timestamp and the unit is ms.                                                                                                                                                                                       |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | Rollup aggregates the raw data generated within a period to the start time of the period. Therefore, if **from** and **to** are within a period, the query result will be empty due to the rollup failure. Set **from** to at least one period earlier than the current time. |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | Take the 5-minute period as an example. If it is 10:35 now, the raw data generated between 10:30 and 10:35 will be aggregated to 10:30. Therefore, in this example, if **period** is 5 minutes, **from** should be 10:30.                                                     |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | .. note::                                                                                                                                                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 |    Cloud Eye rounds up **from** based on the level of granularity required to perform the rollup.                                                                                                                                                                             |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | to              | Yes             | String          | Specifies the end time of the query.                                                                                                                                                                                                                                          |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | The time is a UNIX timestamp and the unit is ms.                                                                                                                                                                                                                              |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | **from** must be earlier than **to**.                                                                                                                                                                                                                                         |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | period          | Yes             | Integer         | Specifies how often Cloud Eye aggregates data, which can be                                                                                                                                                                                                                   |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | -  **1**: Cloud Eye performs no aggregation and displays raw data.                                                                                                                                                                                                            |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | -  **300**: Cloud Eye aggregates data every 5 minutes.                                                                                                                                                                                                                        |
      |                 |                 |                 | -  **1200**: Cloud Eye aggregates data every 20 minutes.                                                                                                                                                                                                                      |
      |                 |                 |                 | -  **3600**: Cloud Eye aggregates data every 1 hour.                                                                                                                                                                                                                          |
      |                 |                 |                 | -  **14400**: Cloud Eye aggregates data every 4 hours.                                                                                                                                                                                                                        |
      |                 |                 |                 | -  **86400**: Cloud Eye aggregates data every 24 hours.                                                                                                                                                                                                                       |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | filter          | Yes             | String          | Specifies the data rollup method, which can be                                                                                                                                                                                                                                |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | -  **average**: Cloud Eye calculates the average value of metric data within a rollup period.                                                                                                                                                                                 |
      |                 |                 |                 | -  **max**: Cloud Eye calculates the maximum value of metric data within a rollup period.                                                                                                                                                                                     |
      |                 |                 |                 | -  **min**: Cloud Eye calculates the minimum value of metric data within a rollup period.                                                                                                                                                                                     |
      |                 |                 |                 | -  **sum**: Cloud Eye calculates the sum of metric data within a rollup period.                                                                                                                                                                                               |
      |                 |                 |                 | -  **variance**: Cloud Eye calculates the variance value of metric data within a rollup period.                                                                                                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | .. note::                                                                                                                                                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 |    Rollup uses a rollup method to aggregate raw data generated within a specific period. Take the 5-minute period as an example. If it is 10:35 now, the raw data generated between 10:30 and 10:35 will be aggregated to 10:30.                                              |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dim             | Yes             | String          | A maximum of three metric dimensions are supported, and the dimensions are numbered from 0 in the **dim.{i}=key,value** format. **key** cannot exceed 32 characters and **value** cannot exceed 256 characters.                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | The following dimensions are only examples. For details about whether multiple dimensions are supported, see the dimension description in the :ref:`monitoring indicator description of each service <ces_03_0059>`.                                                          |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | Single dimension: **dim.0=instance_id,i-12345**                                                                                                                                                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                               |
      |                 |                 |                 | Multiple dimensions: **dim.0=instance_id,i-12345&dim.1=instance_name,i-1234**                                                                                                                                                                                                 |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. note::

      -  **dimensions** can be obtained from the response body by calling the API for :ref:`Querying Metrics <ces_03_0023>`.
      -  OBS metric data can be queried only when the related OBS APIs are called.

-  Example:

   Request example 1: View the CPU usage of ECS whose ID is **6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d** from 2019-04-30 20:00:00 to 2019-04-30 22:00:00. The monitoring interval is 20 minutes.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/metric-data?namespace=SYS.ECS&metric_name=cpu_util&dim.0=instance_id,6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d&from=1556625600000&to=1556632800000&period=1200&filter=min

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 3** Response parameters

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                           |
      +=======================+=======================+=======================================================================================================================================================================================================+
      | datapoints            | Array of objects      | Specifies the metric data list. For details, see :ref:`Table 4 <ces_03_0033__table1017018361914>`.                                                                                                    |
      |                       |                       |                                                                                                                                                                                                       |
      |                       |                       | Since Cloud Eye rounds up **from** based on the level of granularity for data query, **datapoints** may contain more data points than expected.                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name           | String                | Specifies the metric ID. For example, if the monitoring metric of an ECS is CPU usage, **metric_name** is **cpu_util**. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0033__table1017018361914:

   .. table:: **Table 4** **datapoints** data structure description

      +-----------+--------+---------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                     |
      +===========+========+=================================================================================+
      | average   | double | Specifies the average value of metric data within a rollup period.              |
      +-----------+--------+---------------------------------------------------------------------------------+
      | max       | double | Specifies the maximum value of metric data within a rollup period.              |
      +-----------+--------+---------------------------------------------------------------------------------+
      | min       | double | Specifies the minimum value of metric data within a rollup period.              |
      +-----------+--------+---------------------------------------------------------------------------------+
      | sum       | double | Specifies the sum of metric data within a rollup period.                        |
      +-----------+--------+---------------------------------------------------------------------------------+
      | variance  | double | Specifies the variance of metric data within a rollup period.                   |
      +-----------+--------+---------------------------------------------------------------------------------+
      | timestamp | long   | Specifies when the metric is collected. It is a UNIX timestamp in milliseconds. |
      +-----------+--------+---------------------------------------------------------------------------------+
      | unit      | String | Specifies the metric unit.                                                      |
      +-----------+--------+---------------------------------------------------------------------------------+

-  Example response

   Example response 1: The dimension is SYS.ECS, and the average CPU usage of ECSs is displayed.

   .. code-block::

      {
          "datapoints": [
              {
                  "average": 0.23,
                  "timestamp": 1442341200000,
                  "unit": "%"
              }
          ],
          "metric_name": "cpu_util"
      }

   Example response 2: The dimension is SYS.ECS, and the sum CPU usage of ECSs is displayed.

   .. code-block::

      {
          "datapoints": [
              {
                  "sum": 0.53,
                  "timestamp": 1442341200000,
                  "unit": "%"
              }
          ],
          "metric_name": "cpu_util"
      }

   Example response 3: The dimension is SYS.ECS, and the maximum CPU usage of ECSs is displayed.

   .. code-block::

      {
          "datapoints": [
              {
                  "max": 0.13,
                  "timestamp": 1442341200000,
                  "unit": "%"
              }
          ],
          "metric_name": "cpu_util"
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
