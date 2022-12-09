:original_name: ces_03_0023.html

.. _ces_03_0023:

Querying Metrics
================

Function
--------

This API is used to query the metrics. You can specify the namespace, metric, dimension, sorting order, start records, and the maximum number of records when using this API to query metrics.

URI
---

GET /V1.0/{project_id}/metrics

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

      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                           |
      +=================+=================+=================+=======================================================================================================================================================================================================+
      | namespace       | No              | String          | Query the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                       |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | The namespace must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_).    |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metric_name     | No              | String          | Specifies the metric ID. For example, if the monitoring metric of an ECS is CPU usage, **metric_name** is **cpu_util**. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dim             | No              | String          | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about each service dimension, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | A maximum of three dimensions are supported, and the dimensions are numbered from 0 in **dim.{i}=key,value** format. **key** cannot exceed 32 characters and **value** cannot exceed 256 characters.  |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | Single dimension: **dim.0=instance_id,6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d**                                                                                                                          |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | Multiple dimensions: **dim.0=key,value&dim.1=key,value**                                                                                                                                              |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | start           | No              | String          | Specifies the paging start value.                                                                                                                                                                     |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | The format is **namespace.metric_name.key:value**.                                                                                                                                                    |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | Example: **start=SYS.ECS.cpu_util.instance_id:d9112af5-6913-4f3b-bd0a-3f96711e004d**.                                                                                                                 |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit           | No              | Integer         | Supported range: **1** to **1000** (default)                                                                                                                                                          |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | This parameter is used to limit the number of query results.                                                                                                                                          |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | order           | No              | String          | Specifies the result sorting method, which is sorted by timestamp.                                                                                                                                    |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | The default method is **desc**.                                                                                                                                                                       |
      |                 |                 |                 |                                                                                                                                                                                                       |
      |                 |                 |                 | -  **asc**: The query results are displayed in the ascending order.                                                                                                                                   |
      |                 |                 |                 | -  **desc**: The query results are displayed in the descending order.                                                                                                                                 |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example requests

   Example request 1: Query all metrics that can be monitored.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/metrics

   Example request 2: Query the CPU usage of the ECS whose ID is **6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d**. Retain 10 records in descending order by timestamp.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/metrics?namespace=SYS.ECS&metric_name=cpu_util&dim.0=instance_id,6f3c6f91-4b24-4e1b-b7d1-a94ac1cb011d&limit=10&order=desc

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 3** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                    |
      +=======================+=======================+================================================================================+
      | metrics               | Array of objects      | Specifies the list of metric objects.                                          |
      |                       |                       |                                                                                |
      |                       |                       | For details, see :ref:`Table 4 <ces_03_0023__table363011386367>`.              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | meta_data             | Object                | Specifies the metadata of query results, including the pagination information. |
      |                       |                       |                                                                                |
      |                       |                       | For details, see :ref:`Table 6 <ces_03_0023__table2048015400368>`.             |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+

   .. _ces_03_0023__table363011386367:

   .. table:: **Table 4** **metrics** data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                        |
      +=======================+=======================+====================================================================+
      | namespace             | String                | Specifies the metric namespace.                                    |
      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | dimensions            | Array of objects      | Specifies the list of metric dimensions.                           |
      |                       |                       |                                                                    |
      |                       |                       | For details, see :ref:`Table 5 <ces_03_0023__table2024213426364>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | metric_name           | String                | Specifies the metric name, such as **cpu_util**.                   |
      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | unit                  | String                | Specifies the metric unit.                                         |
      +-----------------------+-----------------------+--------------------------------------------------------------------+

   .. _ces_03_0023__table2024213426364:

   .. table:: **Table 5** **dimensions** data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================================================================+
      | name                  | String                | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimension of each service, see the **key** column in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value                 | String                | Specifies the dimension value, for example, an ECS ID.                                                                                                                                                              |
      |                       |                       |                                                                                                                                                                                                                     |
      |                       |                       | Enter 1 to 256 characters.                                                                                                                                                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0023__table2048015400368:

   .. table:: **Table 6** **meta_data** data structure description

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                                                            |
      +=======================+=======================+========================================================================================================================================================================================================================+
      | count                 | Integer               | Specifies the number of returned results.                                                                                                                                                                              |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | marker                | String                | Specifies the pagination marker.                                                                                                                                                                                       |
      |                       |                       |                                                                                                                                                                                                                        |
      |                       |                       | For example, you have queried 10 records this time and the tenth record is about **cpu_util**. In your next query, if **start** is set to **cpu_util**, you can start your query from the next metric of **cpu_util**. |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | total                 | Integer               | Specifies the total number of metrics.                                                                                                                                                                                 |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "metrics": [
              {
                  "namespace": "SYS.ECS",
                  "dimensions": [
                      {
                          "name": "instance_id",
                          "value": "d9112af5-6913-4f3b-bd0a-3f96711e004d"
                      }
                  ],
                  "metric_name": "cpu_util",
                  "unit": "%"
              }
          ],
          "meta_data": {
              "count": 1,
              "marker": "SYS.ECS.cpu_util.instance_id:d9112af5-6913-4f3b-bd0a-3f96711e004d",
              "total": 7
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
