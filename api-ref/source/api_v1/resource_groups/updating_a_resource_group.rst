:original_name: ces_03_0071.html

.. _ces_03_0071:

Updating a Resource Group
=========================

Function
--------

This API is used to update a resource group. You can use resource groups to manage resources by service, and view monitoring and alarm information by group to ease O&M.

URI
---

PUT /V1.0/{project_id}/resource-groups/{group_id}

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                                                                                      |
      +=================+=================+=================+==================================================================================================+
      | project_id      | String          | Yes             | Specifies the project ID.                                                                        |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | Minimum: **1**                                                                                   |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | Maximum: **64**                                                                                  |
      |                 |                 |                 |                                                                                                  |
      |                 |                 |                 | **Regular expression matching**: ^[a-zA-Z0-9-]{1,64}$                                            |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+
      | group_id        | String          | Yes             | Specifies the resource group ID.                                                                 |
      +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+

-  Request example

   .. code-block:: text

      PUT https://{Cloud Eye endpoint}/V1.0/{project_id}/resource-groups/{group_id}

Request
-------

-  Request parameters

   .. table:: **Table 2** Request parameters

      +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type             | Mandatory       | Description                                                                                                                                                         |
      +=================+==================+=================+=====================================================================================================================================================================+
      | group_name      | String           | Yes             | Specifies the resource group name. Enter 1 to 128 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed. Example: **ResourceGroup-Test01** |
      +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resources       | Array of objects | No              | Specifies resources in the resource group.                                                                                                                          |
      |                 |                  |                 |                                                                                                                                                                     |
      |                 |                  |                 | For details, see :ref:`Table 3 <ces_03_0071__table39152528252>`.                                                                                                    |
      +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0071__table39152528252:

   .. table:: **Table 3** **resources** data structure description

      +-----------------+------------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type             | Mandatory       | Description                                                                                                                                                                              |
      +=================+==================+=================+==========================================================================================================================================================================================+
      | namespace       | String           | Yes             | Specifies the resource namespace. For example, the ECS namespace is **SYS.ECS**. To view the namespace of each service, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------------+------------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | dimensions      | Array of objects | Yes             | Specifies one or more resource dimensions.                                                                                                                                               |
      |                 |                  |                 |                                                                                                                                                                                          |
      |                 |                  |                 | For details, see :ref:`Table 4 <ces_03_0071__table9206172582612>`.                                                                                                                       |
      +-----------------+------------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0071__table9206172582612:

   .. table:: **Table 4** **dimensions** data structure description

      +-----------+--------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type   | Mandatory | Description                                                                                                                                                                                   |
      +===========+========+===========+===============================================================================================================================================================================================+
      | name      | String | Yes       | Specifies the resource dimension. For example, the ECS dimension is **instance_id**. To view the dimension of each resource, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
      +-----------+--------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value     | String | Yes       | Specifies the resource dimension value, which is the instance ID. Example: **4270ff17-aba3-4138-89fa-820594c39755**                                                                           |
      +-----------+--------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block::

      {
         "group_name": "Resource-Group-Test01",
         "resources": [
             {
                 "namespace": "SYS.ECS",
                 "dimensions": [
                     {
                         "name": "instance_id",
                         "value": "063a83da-a2b5-4630-ab6b-9b4fcfc261ea"
                     }
                 ]
             },
             {
                 "namespace": "SYS.ECS",
                 "dimensions": [
                     {
                         "name": "instance_id",
                         "value": "518ace88-abde-46bf-829b-0d1f0f2fb2e9"
                     }
                 ]
             },
             {
                 "namespace": "SYS.ECS",
                 "dimensions": [
                     {
                         "name": "instance_id",
                         "value": "675006b5-477a-4aab-948c-0aa467de9c68"
                     }
                 ]
             }
         ]
      }

Response
--------

None

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
