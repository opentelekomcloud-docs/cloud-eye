:original_name: ces_03_0068.html

.. _ces_03_0068:

Querying Resources in a Resource Group
======================================

Function
--------

This API is used to query resources in a resource group based on the resource group ID.

URI
---

GET /V1.0/{project_id}/resource-groups/{group_id}

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                                                                                                                   |
      +=======================+=======================+===============================================================================================================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                                                                                                                     |
      |                       |                       |                                                                                                                                                                                               |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`.                                                                                              |
      |                       |                       |                                                                                                                                                                                               |
      |                       |                       | Minimum: **1**                                                                                                                                                                                |
      |                       |                       |                                                                                                                                                                                               |
      |                       |                       | Maximum: **64**                                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                               |
      |                       |                       | **Regular expression matching**: ^[a-zA-Z0-9-]{1,64}$                                                                                                                                         |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | group_id              | Yes                   | Specifies the resource group ID.                                                                                                                                                              |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | No                    | Specifies the resource health status. The value can be:                                                                                                                                       |
      |                       |                       |                                                                                                                                                                                               |
      |                       |                       | -  **health**: No alarms have been generated for the resource group.                                                                                                                          |
      |                       |                       | -  **unhealth**: An alarm or alarms have been generated for a resource or resources in the resource group.                                                                                    |
      |                       |                       | -  **no_alarm_rule**: No alarm rules have been set for the resource group.                                                                                                                    |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | namespace             | No                    | Specifies the resource namespace. For example, the ECS namespace is **SYS.ECS**. To view the namespace of each service, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.      |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dname                 | No                    | Specifies the resource dimension. For example, the ECS dimension is **instance_id**. To view the dimension of each resource, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      |                       |                       |                                                                                                                                                                                               |
      |                       |                       | This parameter must be used together with the **namespace** parameter.                                                                                                                        |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | start                 | No                    | Specifies the start value of pagination. The value is an integer. The default value is **0**.                                                                                                 |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit                 | No                    | Specifies the maximum number of records that can be queried at a time. The value range is (0,100] and the default value is **100**.                                                           |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example: Query resources in a resource group.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/resource-groups/{group_id}

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 2** Response parameters

      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                            |
      +=======================+=======================+========================================================================================================================================+
      | group_name            | String                | Specifies the resource group, for example, **Resource-Group-ECS-01**.                                                                  |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | group_id              | String                | Specifies the resource group ID, for example, **rg1603786526428bWbVmk4rP**.                                                            |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | resources             | Array of objects      | Specifies information about one or more resource groups.                                                                               |
      |                       |                       |                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 3 <ces_03_0068__table10571837131516>`.                                                                    |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the resource group status, which can be **health**, **unhealth**, or **no_alarm_rule**.                                      |
      |                       |                       |                                                                                                                                        |
      |                       |                       | -  **health**: No alarms have been generated for the resource group.                                                                   |
      |                       |                       | -  **unhealth**: An alarm or alarms have been generated for a resource or resources in the resource group.                             |
      |                       |                       | -  **no_alarm_rule**: No alarm rules have been set for the resource group.                                                             |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | create_time           | Long                  | Specifies the time when the resource group was created. The value is a UNIX timestamp, in milliseconds. Example: **1603819753000**     |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | meta_data             | MetaData object       | Specifies the metadata of query results, including the pagination information.                                                         |
      |                       |                       |                                                                                                                                        |
      |                       |                       | For details, see :ref:`Table 5 <ces_03_0068__table7554143164419>`.                                                                     |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | String                | Specifies the enterprise project associated with the resource group. The default value **0** indicates enterprise project **default.** |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0068__table10571837131516:

   .. table:: **Table 3** **resources** data structure description

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                              |
      +=======================+=======================+==========================================================================================================================================================================================+
      | namespace             | String                | Specifies the resource namespace. For example, the ECS namespace is **SYS.ECS**. To view the namespace of each service, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions            | Array of objects      | Specifies one or more resource dimensions.                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                          |
      |                       |                       | For details, see :ref:`Table 4 <ces_03_0068__table19174559133918>`.                                                                                                                      |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the resource group status, which can be **health**, **unhealth**, or **no_alarm_rule**.                                                                                        |
      |                       |                       |                                                                                                                                                                                          |
      |                       |                       | **health**: No alarms have been generated for the resource group.                                                                                                                        |
      |                       |                       |                                                                                                                                                                                          |
      |                       |                       | **unhealth**: An alarm or alarms have been generated for a resource or resources in the resource group.                                                                                  |
      |                       |                       |                                                                                                                                                                                          |
      |                       |                       | **no_alarm_rule**: No alarm rules have been set for the resource group.                                                                                                                  |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | event_type            | Integer               | Specifies the event type. The default value is **0**.                                                                                                                                    |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0068__table19174559133918:

   .. table:: **Table 4** **dimensions** data structure description

      +-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                                                                                                                                   |
      +===========+========+===============================================================================================================================================================================================+
      | name      | String | Specifies the resource dimension. For example, the ECS dimension is **instance_id**. To view the dimension of each resource, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Specifies the resource dimension value, which is the instance ID. Example: **4270ff17-aba3-4138-89fa-820594c39755**                                                                           |
      +-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0068__table7554143164419:

   .. table:: **Table 5** **meta_data** data structure description

      ========= ======= ============================================
      Parameter Type    Description
      ========= ======= ============================================
      count     Integer Specifies the number of returned results.
      total     Integer Specifies the total number of query results.
      marker    String  Specifies the pagination marker.
      ========= ======= ============================================

   -  Example response

      .. code-block::

         {
          "group_name": "ResourceGroup-Test-01",
          "resources": [
            {
              "namespace": "SYS.ECS",
              "dimensions": [
                {
                  "name": "instance_id",
                  "value": "6cffb0bd-fd37-400f-ae6f-8f4be021ff7e"
                }
              ],
              "status": "health",
              "event_type": 0
            },
            {
              "namespace": "SYS.ECS",
              "dimensions": [
                {
                  "name": "instance_id",
                  "value": "e37d6238-9dd3-4720-abcc-eb9f8fb08ca0"
                }
              ],
              "status": "health",
              "event_type": 0
            }
          ],
          "create_time": 1604476378000,
          "group_id": "rg16044763786104XvXvl00a",
          "status": "health",
          "meta_data": {
            "count": 0,
            "marker": "",
            "total": 2
          },
          "enterprise_project_id": "0"
         }

Returned Values
---------------

-  Normal

   200

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
