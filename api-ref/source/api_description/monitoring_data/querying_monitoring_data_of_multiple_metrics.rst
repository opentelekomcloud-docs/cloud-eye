:original_name: ces_03_0034.html

.. _ces_03_0034:

Querying Monitoring Data of Multiple Metrics
============================================

Function
--------

You can query the monitoring data of specified metrics within a specified time range and at a specified granularity. You can query the monitoring data of up to 10 metrics in one batch.

URI
---

POST /V1.0/{project_id}/batch-query-metric-data

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

   #. The default maximum query intervals of different periods are different.

      If **period** is **1**, the maximum interval between **from** and **to** is 4 hours. If the interval between **from** and **to** is longer than 4 hours, adjust the value of **from** to **to** - **4*3600*1000**.

      If **period** is **300**, the maximum interval between **from** and **to** is one day. If the interval between **from** and **to** is longer than one day, adjust the value of **from** to **to** - **24*3600*1000**.

      If **period** is **1200**, the maximum interval between **from** and **to** is three days. If the interval between **from** and **to** is longer than three days, adjust the value of **from** to **to** - **3*24*3600*1000**.

      If **period** is **3600**, the maximum interval between **from** and **to** is 10 days. If the interval between **from** and **to** is longer than 10 days, adjust the value of **from** to **to** - **10*24*3600*1000**.

      If **period** is **14400**, the maximum interval between **from** and **to** is 30 days. If the interval between **from** and **to** is longer than 30 days, adjust the value of **from** to **to** - **30*24*3600*1000**.

      If **period** is **86400,** the maximum interval between **from** and **to** is 180 days. If the interval between **from** and **to** is longer than 180 days, adjust the value of **from** to **to** - **180*24*3600*1000**.

-  Request parameters

   .. table:: **Table 2** Request parameters

      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
      +=================+=================+==================+==============================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
      | metrics         | Yes             | Array of objects | Specifies the metric data. The maximum length of the array is 10.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  | For details, see :ref:`Table 3 <ces_03_0034__table53651023191739>`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | from            | Yes             | Long             | Specifies the start time of the query. The time is a UNIX timestamp and the unit is ms. Set **from** to at least one period earlier than the current time. Rollup aggregates the raw data generated within a period to the start time of the period. If **from** and **to** are within a period, the query result will be empty due to the rollup failure. Set **from** to at least one period earlier than the current time. Take the 5-minute period as an example. If it is 10:35 now, the raw data generated between 10:30 and 10:35 will be aggregated to 10:30. In this example, if **period** is 5 minutes, **from** should be 10:30. |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  | .. note::                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  |    Cloud Eye rounds up **from** based on the level of granularity required to perform the rollup.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | to              | Yes             | Long             | Specifies the end time of the query. The time is a UNIX timestamp and the unit is ms. **from** must be earlier than **to**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | period          | Yes             | String           | Specifies how often Cloud Eye aggregates data, which can be                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  | -  **1**: Cloud Eye performs no aggregation and displays raw data.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
      |                 |                 |                  | -  **300**: Cloud Eye aggregates data every 5 minutes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
      |                 |                 |                  | -  **1200**: Cloud Eye aggregates data every 20 minutes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
      |                 |                 |                  | -  **3600**: Cloud Eye aggregates data every hour.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
      |                 |                 |                  | -  **14400**: Cloud Eye aggregates data every 4 hours.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
      |                 |                 |                  | -  **86400**: Cloud Eye aggregates data every 24 hours.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | filter          | Yes             | String           | Specifies the data rollup method, which can be                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  | -  **average**: Cloud Eye calculates the average value of metric data within a rollup period.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
      |                 |                 |                  | -  **max**: Cloud Eye calculates the maximum value of metric data within a rollup period.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
      |                 |                 |                  | -  **min**: Cloud Eye calculates the minimum value of metric data within a rollup period.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
      |                 |                 |                  | -  **sum**: Cloud Eye calculates the sum of metric data within a rollup period.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  | -  **variance**: Cloud Eye calculates the variance value of metric data within a rollup period.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      |                 |                 |                  | **filter** does not affect the query result of raw data. (The period is **1**.)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
      +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0034__table53651023191739:

   .. table:: **Table 3** **metrics** data structure description

      +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type             | Description                                                                                                                                                                                           |
      +=================+=================+==================+=======================================================================================================================================================================================================+
      | namespace       | Yes             | String           | Specifies the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                   |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | The namespace must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_).    |
      +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name     | Yes             | String           | Specifies the metric ID. For example, if the monitoring metric of an ECS is CPU usage, **metric_name** is **cpu_util**. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | The value must start with a letter. Enter 1 to 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                     |
      +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions      | Yes             | Array of objects | Specifies metric dimensions. **dimensions** is an array consisting of a maximum of four JSON objects.                                                                                                 |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | One dimension is a JSON object, and its structure is as follows:                                                                                                                                      |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | {                                                                                                                                                                                                     |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | "name": "instance_id",                                                                                                                                                                                |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | "value": "33328f02-3814-422e-b688-bfdba93d4050"                                                                                                                                                       |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | }                                                                                                                                                                                                     |
      |                 |                 |                  |                                                                                                                                                                                                       |
      |                 |                 |                  | For details, see :ref:`Table 4 <ces_03_0034__table346618584132>`.                                                                                                                                     |
      +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0034__table346618584132:

   .. table:: **Table 4** **dimensions** data structure description

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                         |
      +=================+=================+=================+=====================================================================================================================================================================================================================+
      | name            | Yes             | String          | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 | Start with a letter. Enter 1 to 32 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                  |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value           | Yes             | String          | Specifies the dimension value, for example, an ECS ID. **dimensions** can be obtained from the response body by calling the API for :ref:`querying metrics <ces_03_0023>`.                                          |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 | Start with a letter or a digit. Enter 1 to 256 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                      |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. note::

      -  **dimensions** can be obtained from the response body by calling the API for :ref:`querying metrics <ces_03_0023>`.
      -  OBS metric data can be queried only when the related OBS APIs are called.

-  Example request

   Request example 1: Query the average disk usage of the OS on the ECS whose **instance_id** is **07d878a9-2243-4e84-aeef-c47747d18024** and **mount_point** is **012bec14bc176310c19f40e384fd629b** from 20:00:00 to 22:00:00 on April 30, 2019.

   .. code-block::

      {
          "from": 1556625600000,
          "to": 1556632800000,
          "period": "1",
          "filter": "average",
          "metrics": [{
              "dimensions": [{
                  "name": "instance_id",
                  "value": "07d878a9-2243-4e84-aeef-c47747d18024"
              }, {
                  "name": "mount_point",
                  "value": "012bec14bc176310c19f40e384fd629b"
              }],
              "metric_name": "disk_usedPercent",
              "namespace": "AGT.ECS"
          }]
      }

   Request example 2: Query the average memory usage of the OS of the ECS whose **instance_id** is **238764d4-c4e1-4274-88a1-5956b057766b** from 20:00:00 to 22:00:00 on April 30, 2019.

   .. code-block::

      {
          "from": 1556625600000,
          "to": 1556632800000,
          "period": "1",
          "filter": "average",
          "metrics": [{
              "dimensions": [{
                  "name": "instance_id",
                  "value": "238764d4-c4e1-4274-88a1-5956b057766b"
              }],
              "metric_name": "mem_usedPercent",
              "namespace": "AGT.ECS"
          }]
      }

   Request example 3: Query the average **cpu_util** of the five ECSs whose **instance_id** are **faea5b75-e390-4e2b-8733-9226a9026070**, **faea5b75-e390-4e2b-8733-9226a9026071**, **faea5b75-e390-4e2b-8733-9226a9026072**, **faea5b75-e390-4e2b-8733-9226a9026073**, and **faea5b75-e390-4e2b-8733-9226a9026074** from 00:00:00 to 23:59:59 on August 21, 2024. Query five metrics. The monitoring period is 60,000 ms. The maximum value of (**to**\ ``-``\ **from**) is 36,000,000. The value of the request parameter (**to**\ ``-``\ **from**) is 86,399,000, which exceeds the maximum value 36,000,000. The formula is as follows: The number of metrics x (**to**\ ``-``\ **from**)/Monitoring period <= 3000. The value of **from** in the request parameter is automatically changed to **to**-36,000,000, that is, 1,724,219,999,000.

   .. code-block::

      {
          "metrics": [
             {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026070"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
             {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026071"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
                     {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026072"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
                     {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026073"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
                     {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026074"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
          ],
          "from": 1724169600000,
          "to": 1724255999000,
          "period": "1",
          "filter": "average"
      }

   Request example 4: View the average **cpu_util** of the ECS whose **instance_id** is **faea5b75-e390-4e2b-8733-9226a9026070** and the average **network_vm_connections** of the ECS whose **instance_id** is **06b4020f-461a-4a52-84da-53fa71c2f42b**. The monitoring data was collected from 20:00:00 to 22:00:00 on April 30, 2019.

   .. code-block::

      {
          "metrics": [
             {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026070"
                      }
                  ],
                  "metric_name": "cpu_util"
              },
              {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "06b4020f-461a-4a52-84da-53fa71c2f42b"
                      }
                  ],
                  "metric_name": "network_vm_connections"
              }
          ],
          "from": 1556625600000,
          "to": 1556632800000,
          "period": "1",
          "filter": "average"
      }

   Request example 5: View the sums of **rds021_myisam_buf_usage** of the RDS instance whose **rds_cluster_id** is **3c8cc15614ab46f5b8743317555e0de2in01** and the RDS instance whose **rds_cluster_id** is **3b2fa8b55a9b4adca3713962a9d31884in01**. The monitoring data was collected from 20:00:00 to 22:00:00 on April 30, 2019.

   .. code-block::

      {
          "metrics": [
              {
                  "namespace": "SYS.RDS",
                  "dimensions": [
                      {
                          "name": "rds_cluster_id",
                          "value": "3c8cc15614ab46f5b8743317555e0de2in01"
                      }
                  ],
                  "metric_name": "rds021_myisam_buf_usage"
              },
              {
                  "namespace": "SYS.RDS",
                  "dimensions": [
                      {
                          "name": "rds_cluster_id",
                          "value": "3b2fa8b55a9b4adca3713962a9d31884in01"
                      }
                  ],
                  "metric_name": "rds021_myisam_buf_usage"
              }
          ],
          "from": 1556625600000,
          "to": 1556632800000,
          "period": "1",
          "filter": "sum"
      }

   Example request 6: View the minimum **proc_specified_count** of the server whose **instance_id** is **cd841102-f6b1-407d-a31f-235db796dcbb** and **proc** is **b28354b543375bfa94dabaeda722927f**. The monitoring data is collected from 20:00:00 to 22:00:00 on April 30, 2019 and the rollup period is 20 minutes.

   .. code-block::

      {
          "metrics": [
              {
                  "namespace": "AGT.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "cd841102-f6b1-407d-a31f-235db796dcbb"
                      },
                      {
                          "name": "proc",
                          "value": "b28354b543375bfa94dabaeda722927"
                      }
                  ],
                  "metric_name": "proc_specified_count"
              }
          ],
          "from": 1556625600000,
          "to": 1556632800000,
          "period": "1200",
          "filter": "min"
      }

Response
--------

-  Response parameters

   .. table:: **Table 5** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                        |
      +=======================+=======================+====================================================================+
      | metrics               | Array of objects      | Specifies the metric data.                                         |
      |                       |                       |                                                                    |
      |                       |                       | For details, see :ref:`Table 6 <ces_03_0034__table8753531192320>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------+

   .. _ces_03_0034__table8753531192320:

   .. table:: **Table 6** **metrics** data structure description

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                                        |
      +=======================+=======================+====================================================================================================================================================================================================================================+
      | unit                  | String                | Specifies the metric unit.                                                                                                                                                                                                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | datapoints            | Array of objects      | Specifies the metric data list. Cloud Eye rounds up the value of **from** based on the selected granularity for data query, so **datapoints** may contain more data points than expected. Up to 3,000 data points can be returned. |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | For details, see :ref:`Table 8 <ces_03_0034__table776113112239>`.                                                                                                                                                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | namespace             | String                | Specifies the metric namespace, which must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_).         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions            | Array of objects      | Specifies the list of metric dimensions.                                                                                                                                                                                           |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | Each dimension is a JSON object, and its structure is as follows:                                                                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | {                                                                                                                                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | "name": "instance_id",                                                                                                                                                                                                             |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | "value": "33328f02-3814-422e-b688-bfdba93d4050"                                                                                                                                                                                    |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | }                                                                                                                                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                                    |
      |                       |                       | For details, see :ref:`Table 7 <ces_03_0034__table14755123118236>`.                                                                                                                                                                |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name           | String                | Specifies the metric name. Start with a letter. Enter 1 to 64 characters. Only letters, digits, and underscores (_) are allowed.                                                                                                   |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0034__table14755123118236:

   .. table:: **Table 7** **dimensions** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================+
      | name                  | String                | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      |                       |                       |                                                                                                                                                                                                                     |
      |                       |                       | Start with a letter. Enter 1 to 32 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                                  |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value                 | String                | Specifies the dimension value, for example, an ECS ID.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                     |
      |                       |                       | Start with a letter or a digit. Enter 1 to 256 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                                                      |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0034__table776113112239:

   .. table:: **Table 8** **datapoints** data structure description

      +-----------+--------+---------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                     |
      +===========+========+=================================================================================+
      | average   | Double | Specifies the average value of metric data within a rollup period.              |
      +-----------+--------+---------------------------------------------------------------------------------+
      | max       | Double | Specifies the maximum value of metric data within a rollup period.              |
      +-----------+--------+---------------------------------------------------------------------------------+
      | min       | Double | Specifies the minimum value of metric data within a rollup period.              |
      +-----------+--------+---------------------------------------------------------------------------------+
      | sum       | Double | Specifies the sum of metric data within a rollup period.                        |
      +-----------+--------+---------------------------------------------------------------------------------+
      | variance  | Double | Specifies the variance of metric data within a rollup period.                   |
      +-----------+--------+---------------------------------------------------------------------------------+
      | timestamp | Long   | Specifies when the metric is collected. It is a UNIX timestamp in milliseconds. |
      +-----------+--------+---------------------------------------------------------------------------------+

-  Example response

   Example response 1: The average **cpu_util** of the ECS whose **instance_id** is **faea5b75-e390-4e2b-8733-9226a9026070** and the average **network_vm_connections** of the ECS whose **instance_id** is **06b4020f-461a-4a52-84da-53fa71c2f42b** are displayed.

   .. code-block::

      {
          "metrics": [
              {
                  "namespace": "SYS.ECS",
                  "metric_name": "cpu_util",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "faea5b75-e390-4e2b-8733-9226a9026070"
                      }
                  ],
                  "datapoints": [
                      {
                          "average": 0.69,
                          "timestamp": 1556625610000
                      },
                      {
                          "average": 0.7,
                          "timestamp": 1556625715000
                      }
                  ],
                  "unit": "%"
              },
              {
                  "namespace": "SYS.ECS",
                  "metric_name": "network_vm_connections",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "06b4020f-461a-4a52-84da-53fa71c2f42b"
                      }
                  ],
                  "datapoints": [
                      {
                          "average": 1,
                          "timestamp": 1556625612000
                      },
                      {
                          "average": 3,
                          "timestamp": 1556625717000
                      }
                  ],
                  "unit": "count"
              }
          ]
      }

   Response example 2: The **rds021_myisam_buf_usage** sums of the RDS instance whose **rds_cluster_id** are **3c8cc15614ab46f5b8743317555e0de2in01** is displayed, and those of the RDS instance whose **rds_cluster_id** is **3b2fa8b55a9b4adca3713962a9d31884in01** are displayed.

   .. code-block::

      {
          "metrics": [
              {
                  "unit": "Ratio",
                  "datapoints": [
                      {
                          "sum": 0.07,
                          "timestamp": 1556625628000
                      },
                      {
                          "sum": 0.07,
                          "timestamp": 1556625688000
                      }
                  ],
                  "namespace": "SYS.RDS",
                  "dimensions": [
                      {
                          "name": "rds_cluster_id",
                          "value": "3c8cc15614ab46f5b8743317555e0de2in01"
                      }
                  ],
                  "metric_name": "rds021_myisam_buf_usage"
              },
              {
                  "unit": "Ratio",
                  "datapoints": [
                      {
                          "sum": 0.06,
                          "timestamp": 1556625614000
                      },
                      {
                          "sum": 0.07,
                          "timestamp": 1556625674000
                      }
                  ],
                  "namespace": "SYS.RDS",
                  "dimensions": [
                      {
                          "name": "rds_cluster_id",
                          "value": "3b2fa8b55a9b4adca3713962a9d31884in01"
                      }
                  ],
                  "metric_name": "rds021_myisam_buf_usage"
              }
          ]
      }

   Response example 3: The minimum **rds021_myisam_buf_usage** of the server whose **instance_id** is **cd841102-f6b1-407d-a31f-235db796dcbb** and **proc** is **b28354b543375bfa94dabaeda722927f** is displayed.

   .. code-block::

      {
          "metrics": [
              {
                  "unit": "Ratio",
                  "datapoints": [
                      {
                          "min": 0,
                          "timestamp": 1556625612000
                      },
                      {
                          "min": 0,
                          "timestamp": 1556625672000
                      }
                  ],
                  "namespace": "AGT.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "cd841102-f6b1-407d-a31f-235db796dcbb"
                      },
                      {
                          "name": "proc",
                          "value": "b28354b543375bfa94dabaeda722927f"
                      }
                  ],
                  "metric_name": "rds021_myisam_buf_usage"
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
