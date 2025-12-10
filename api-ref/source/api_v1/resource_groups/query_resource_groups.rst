:original_name: ces_03_0073.html

.. _ces_03_0073:

Query Resource Groups
=====================

Function
--------

This API is used to query all resource groups you created.

URI
---

GET /V1.0/{project_id}/resource-groups

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                                                                                                        |
      +=================+=================+=================+====================================================================================================================+
      | project_id      | String          | Yes             | Specifies the project ID.                                                                                          |
      |                 |                 |                 |                                                                                                                    |
      |                 |                 |                 | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`.                   |
      |                 |                 |                 |                                                                                                                    |
      |                 |                 |                 | Minimum: **1**                                                                                                     |
      |                 |                 |                 |                                                                                                                    |
      |                 |                 |                 | Maximum: **64**                                                                                                    |
      |                 |                 |                 |                                                                                                                    |
      |                 |                 |                 | **Regular expression matching**: ^[a-zA-Z0-9-]{1,64}$                                                              |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+
      | group_name      | String          | No              | Specifies the resource group, for example, **Resource-Group-ECS-01**.                                              |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+
      | group_id        | String          | No              | Specifies the resource group ID, for example, **rg1603786526428bWbVmk4rP**.                                        |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+
      | status          | String          | No              | Specifies the resource group status, which can be **health**, **unhealth**, or **no_alarm_rule**.                  |
      |                 |                 |                 |                                                                                                                    |
      |                 |                 |                 | -  **health**: No alarms have been generated for the resource group.                                               |
      |                 |                 |                 | -  **unhealth**: An alarm or alarms have been generated for a resource or resources in the resource group.         |
      |                 |                 |                 | -  **no_alarm_rule**: No alarm rules have been set for the resource group.                                         |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+
      | start           | Integer         | No              | Specifies the start value of pagination. The value is an integer. The default value is **0**.                      |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+
      | limit           | Integer         | No              | Specifies the maximum number of records that can be queried at a time. Supported range: **1** to **100** (default) |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------+

-  Example

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/resource-groups

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 2** Response parameters

      +-----------------+------------------+-----------------+---------------------------------------------------------------------+
      | Parameter       | Type             | Mandatory       | Description                                                         |
      +=================+==================+=================+=====================================================================+
      | resource_groups | Array of objects | No              | Specifies information about one or more resource groups.            |
      |                 |                  |                 |                                                                     |
      |                 |                  |                 | For details, see :ref:`Table 3 <ces_03_0073__table10571837131516>`. |
      +-----------------+------------------+-----------------+---------------------------------------------------------------------+
      | meta_data       | MetaData object  | No              | Specifies the number of metadata records in the query result.       |
      |                 |                  |                 |                                                                     |
      |                 |                  |                 | For details, see :ref:`Table 5 <ces_03_0073__table7554143164419>`.  |
      +-----------------+------------------+-----------------+---------------------------------------------------------------------+

   .. _ces_03_0073__table10571837131516:

   .. table:: **Table 3** **resource_groups** data structure description

      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                      | Mandatory       | Description                                                                                                                            |
      +=======================+===========================+=================+========================================================================================================================================+
      | group_name            | String                    | No              | Specifies the resource group name, for example, **ResourceGroup-Test01**.                                                              |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | group_id              | String                    | No              | Specifies the resource group ID, for example, **rg1603786526428bWbVmk4rP**.                                                            |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | create_time           | Long                      | No              | Specifies the time when the resource group was created. The value is a UNIX timestamp, in milliseconds. Example: **1603819753000**     |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | relation_ids          | Array of strings          | No              | Specifies the enterprise project IDs.                                                                                                  |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | type                  | String                    | No              | Specifies the method of adding or matching resources to a resource group.                                                              |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | The value can be:                                                                                                                      |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | **EPS**: matching resources by enterprise project.                                                                                     |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | **TAG**: matching resources by tag.                                                                                                    |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | **NAME**: matching resources by instance name.                                                                                         |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | **COMB**: matching resources by multiple criteria.                                                                                     |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | **Manual**: add resources manually.                                                                                                    |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | If the response parameter is empty, resources are manually added.                                                                      |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | Minimum length: 0 character                                                                                                            |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | Maximum length: 32 characters                                                                                                          |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | resources             | Array of Resource objects | No              | Specifies information about one or more resources.                                                                                     |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | Array length: 0 to 20                                                                                                                  |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | instance_statistics   | InstanceStatistics object | No              | Specifies the resource statistics in the resource group.                                                                               |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | For details, see :ref:`Table 4 <ces_03_0073__table19174559133918>`.                                                                    |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                    | No              | Specifies the resource group status, which can be **health**, **unhealth**, or **no_alarm_rule**.                                      |
      |                       |                           |                 |                                                                                                                                        |
      |                       |                           |                 | -  **health**: No alarms have been generated for the resource group.                                                                   |
      |                       |                           |                 | -  **unhealth**: An alarm or alarms have been generated for a resource or resources in the resource group.                             |
      |                       |                           |                 | -  **no_alarm_rule**: No alarm rules have been set for the resource group.                                                             |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | String                    | No              | Specifies the enterprise project associated with the resource group. The default value **0** indicates enterprise project **default.** |
      +-----------------------+---------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0073__table19174559133918:

   .. table:: **Table 4** **instance_statistics** data structure description

      +-----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type    | Mandatory | Description                                                                                                                                                                         |
      +=================+=========+===========+=====================================================================================================================================================================================+
      | unhealth        | Integer | No        | Specifies the number of resources in the **Alarm** state in the resource group.                                                                                                     |
      +-----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | total           | Integer | No        | Specifies the total number of resources in the resource group.                                                                                                                      |
      +-----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | type_statistics | Integer | No        | Specifies the total number of resource types in the resource group. For example, if ECS, EIP and bandwidth are added to the resource group, the **type_statistics** value is **2**. |
      +-----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0073__table7554143164419:

   .. table:: **Table 5** **meta_data** data structure description

      ========= ======= ========= ============================================
      Parameter Type    Mandatory Description
      ========= ======= ========= ============================================
      total     Integer No        Specifies the total number of query results.
      ========= ======= ========= ============================================

   -  Example response

      .. code-block::

         {
           "resource_groups": [
            {
              "group_name": "ResourceGroup-Test01",
              "create_time": 1606374365000,
              "group_id": "rg16063743652226ew93e64p",
              "relation_ids": ["0"],
              "instance_statistics": {
                "unhealth": 2,
                "total": 10,
                "type_statistics": 1
              },
              "status": "unhealth",
              "enterprise_project_id": "0",
              "type": "TAG",
              "resources": []
            },
            {
              "group_name": "RS",
              "create_time": 1606327955000,
              "group_id": "rg1606327955657LRj1lrE4y",
              "relation_ids": ["0"],
              "instance_statistics": {
                "unhealth": 0,
                "total": 2,
                "type_statistics": 1
              },
              "status": "no_alarm_rule",
              "enterprise_project_id": "0",
              "type": "TAG",
              "resources": []
            },
            {
              "group_name": "RS",
              "create_time": 1606327947000,
              "group_id": "rg1606327947514v9OWqAD3N",
              "relation_ids": ["0"],
              "instance_statistics": {
                "unhealth": 0,
                "total": 2,
                "type_statistics": 1
              },
              "status": "no_alarm_rule",
              "enterprise_project_id": "0",
              "type": "TAG",
              "resources": []
            },
            {
              "group_name": "RS",
              "create_time": 1606327946000,
              "group_id": "rg1606327946625PYogr059N",
              "relation_ids": ["0"],
              "instance_statistics": {
                "unhealth": 0,
                "total": 2,
                "type_statistics": 1
              },
              "status": "no_alarm_rule",
              "enterprise_project_id": "0",
              "type": "TAG",
              "resources": []
            },
            {
              "group_name": "ResourceGroupCorrect_2",
              "create_time": 1606325669000,
              "group_id": "rg1606325669900Rk4eKkLMZ",
              "relation_ids": ["0"],
              "instance_statistics": {
                "unhealth": 0,
                "total": 1,
                "type_statistics": 1
              },
              "status": "no_alarm_rule",
              "enterprise_project_id": "0",
              "type": "TAG",
              "resources": []
            }
          ],
          "meta_data": {
            "total": 5
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
